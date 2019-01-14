Broadcom Bluetooth driver using:
--
for DW1560, we need install neccessary drivers *BrcmFirmwareRepo.kext* *BrcmPatchRAM2.kext* into L/E dir
for audio combo-jack, need install driver *CodecCommander.kext* into L/E
all need rebuild kextcacke and reboot for active :
`sudo kextcache -i /`
