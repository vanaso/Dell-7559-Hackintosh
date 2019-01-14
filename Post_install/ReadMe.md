## Here explain all neccessary drivers for the hardware on this Hackintosh
    specially, the wifi & bluetooth card is DW1560(Broadcom 94352Z), make adjustment when your card different
ALL NECCESSARY DRIVERS MUST INSTALL INTO **/Library/Extensions**
Broadcom Bluetooth driver:
--
DW1560: **BrcmFirmwareRepo.kext、BrcmPatchRAM2.kext**

Audio combo-jack driver：
--
**CodecCommander.kext**

Do Rebuild kextcacke:
--
    some drivers native after reboot
`sudo kextcache -i /`
