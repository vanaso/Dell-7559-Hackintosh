## Here explain all neccessary drivers for the hardware on this Hackintosh
    specially, the wifi & bluetooth card is DW1560(Broadcom 94352Z), make adjustment when your card different
kexts mark ✅ require install into **/Library/Extensions** and rebuild cache.

Broadcom Bluetooth driver:
--
✅**BrcmFirmwareRepo.kext、BrcmPatchRAM2.kext**

Broadcom Wi-Fi driver:
--
*AirportBrcmFixup.kext、FakePCIID_Broadcom_WiFi.kext、FakePCIID.kext*

Audio combo-jack driver：
--
✅**CodecCommander.kext** 
  
AppleALC.kext、Lilu.kext
⚠️*FakePCIID_Intel_HDMI_Audio.kext only make sense when using BIOS V1.0.1*

Graphic video play about：
-- 
✅**IntelGraphicsFixup.kext**  
fixed web video crash via safari , whatevergreen make no sense to replace

RealtekWlan：
--
*RealtekRTL8111.kext*

Do Rebuild kextcacke:
--
    some drivers native after reboot
`sudo kextcache -i /`
