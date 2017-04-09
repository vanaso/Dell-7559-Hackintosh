# This branch only work for Serria (10.12.4 or later)
## new methon to fix HD530 backlight control(from RehabMan):
  >>https://www.tonymacx86.com/threads/guide-laptop-backlight-control-using-applebacklightinjector-kext.218222/
  
### change:
  
  remove the brightnessfix patch frome DSDT.aml
  
  enable SSDT-PNLF.aml adn SSDT-Config.aml to get the newway patch work smoothly
  
  replace IntelBacklight.kext by AppleBacklightInjector.kext
  
  All above chage file upload(only for Dell 7559 i5 6300HQ)
