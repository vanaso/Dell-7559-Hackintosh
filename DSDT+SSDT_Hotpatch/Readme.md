#### In this part, include patched DSDT.aml and SSDT*.aml

    Patched DSDT.aml include normaly ACPI fix and patches, for some specially function patch—— their need additonal patched SSDT.aml ACPI files, That what I call Necessary Pathced SSDT*.aml ACPI files
Necessary ACPI files:
`SSDT-PNLF` For Backlight control(support OS 12.6+) do not apply brightness fix into DSDT.aml
`SSDT-UIAC-ALL`   For USB inject(support OS 11.4+)

Patches from this [GUIDE](https://www.tonymacx86.com/threads/guide-dell-inspiron-15-7559-sierra-high-sierra-install.201576/) :  

###### Rename :
    HECI to IMEI
    HDAS to HDEF
###### Patched:
    [syn] Rename _DSM methods to XDSM
    [Audio] Audio Layout 3
    [bat] Dell Inspiron 15-7xxx
    [sys] Fix _WAK Arg0 v2 (may not be necessary after 10.12.2)
    [sys] Fix Mutex with non-zero SyncLevel
    [sys] HPET Fix
    [sys] IRQ fix
    [sys] RTC Fix
    [sys] Skylake LPC
    [sys] SMBUS Fix
    [usb] USB3_PRW 0x6D Skylake
###### Disable nvidia for better battery (advised - needed for High Sierra install )
Add these lines above the other External lines at the beginning:
```ash
External (_SB_.PCI0.PEG0.PEGP._PS3, MethodObj)
External (_SB_.PCI0.PEG0.PEGP._PS0, MethodObj)
External (_SB_.PCI0.PEG0.PEGP._OFF, MethodObj)
External (_SB_.PCI0.PEG0.PEGP._ON, MethodObj)
External (_SB_.PCI0.PEG0.PEGP.SGOF, MethodObj)
External (_SB_.PCI0.PEG0.PEGP.SGON, MethodObj)
```
Search for `_WAK` and add these methods above `Method (_WAK)`:
```ash
Method (M_ON, 0, NotSerialized)
    {
        If (CondRefOf (\_SB_.PCI0.PEG0.PEGP._ON))
        {
            \_SB_.PCI0.PEG0.PEGP._ON()
        }
        If (CondRefOf (\_SB_.PCI0.PEG0.PEGP._PS0))
        {
            \_SB_.PCI0.PEG0.PEGP._PS0()
        }
        If (CondRefOf (\_SB_.PCI0.PEG0.PEGP.SGON))
        {
            \_SB_.PCI0.PEG0.PEGP.SGON()
        }
    }
Method (M_OF, 0, NotSerialized)
    {
        If (CondRefOf (\_SB_.PCI0.PEG0.PEGP._OFF))
        {
            \_SB_.PCI0.PEG0.PEGP._OFF()
        }
        If (CondRefOf (\_SB_.PCI0.PEG0.PEGP._PS3))
        {
            \_SB_.PCI0.PEG0.PEGP._PS3()
        }
        If (CondRefOf (\_SB_.PCI0.PEG0.PEGP.SGOF))
        {
            \_SB_.PCI0.PEG0.PEGP.SGOF()
        }
    }
```
Add this line right after the opening bracket of `Method (_WAK)`:
```ash
    M_OF ()
```
Search for `_PTS` and add this line right after the opening bracket of `Method (_PTS)`:
```ash 
    M_ON ()
```
Search for the `_INI` where you find references of Linux and Windows. Add this line between` Store (….)` and `If (…..(..))`:
```ash
    M_OF ()
```
###### Diffrent Clover config.plist to Full Hopached method:
    rename GFXO to IGPU in config.plist
    disabl others ACPI/fixs
Others(`kext and kernel/kexts patched`) as same as the full hotpatch method.
