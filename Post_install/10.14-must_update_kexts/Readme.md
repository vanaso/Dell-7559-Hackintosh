## CodecCommander.kext install into L/E
## ⚠️ Important update info ( For Mojave, 27/10/2018 )
  OSX removed some audio layout support, do update to lasted release [AppleALC](https://github.com/acidanthera/AppleALC) + [Lilu](https://github.com/acidanthera/Lilu) to fix audio.
    
  My Dell 7559 i5 6300HQ using Realtek ALC 256 audio codec, change inject layout id, here default `layout=13`.
  
  need `CodecCommander.kext` & `SSDT-ALC256-insanelydeepak.aml` to fix wake earphone audio/wakeup audio, return perfect audio. More details in `CodecCommander.kext⁩/⁨Contents⁩/Resources⁩`. Custom your files or using others aml file for test. 
  Updated in  `10.14-must_update_kexts`

  To fix black screen when install Mojave, Clover config.plist need inject intel Graphic, 
  `Graphics\Inject\Intel` changed `YES`
