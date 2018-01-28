# New hot-patch useage:
## config.plist:A working config for Dell 7559 with only hotpatch method
  Support native power manage、audio、bluetooth、brightness adjust、sleep and wake up.
# kexts:
  Need kexts have to be install:
  Mark blue——default install in EFI/CLOVER/KEXT/OTHERS,if your hardware do not work perfect,try to remove them and install into S/L/E
  Mark orange——default install in EFI/CLOVER/KEXT/OTHERS,alos work in S/L/E.ON YOUR HAND.
  Mark red——must install in EFI/CLOVER/KEXT/OTHERS，otherwise faile to boot.NEVER CHANGE IT!
  "声卡驱动.zip" include 2 kexts，for ALC_256,install it into S/L/E.