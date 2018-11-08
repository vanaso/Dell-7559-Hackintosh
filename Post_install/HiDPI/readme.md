#### This setting profile only for my Dell 7559 FHD screen 16:9.

All resolutions from windows:
```
Win origin      Custom add
1920x1080		
1680x1050
1600x900
            insert 1680x945
1440x900
            insert 1440x810 
1400x1050
1366x768
            insert 1344x756
1360x768		
1280x1024		
1280x960		
1280x800	
1280x768
1280x720
1280x600
1152x864
1024x768
800x600
```
### 5 better perfomence resolutions for Hidpi display:
you may need RDM.app for select resollution
```
1920x1080   00000F00 00000870 00000001 00200000 ✅
1680x945    00000B40 00000654 00000001 00200000 ✅
1600x900    00000D20 00000762 00000001 00200000 ✅
1440x810    00000C80 00000708 00000001 00200000 ✅
1366x768    00000AAC 00000600 00000001 00200000 ✅
1344x756    00000A80 000005E8 00000001 00200000 ✅
```
## Befor apply to system：
Two method to make Hidpi working: first one is writting custom diskplay profile as `Speciall method`; second is `compatible method` by adding defind screen profile.
pick up `compatible method` if you don't want spent times，otherwise custom your display profile.

Lookup `DisplayVerdorID` and `DisplayProductID` in IORegistryExplorer by searching `"display"`.
Take my example, DisplayVendorID is `0x9e5`, DisplayProductID is `0x62f`
create custome Overrides files for your diskpaly in `/System/Library/Displays/Contents/Resources/Overrides/`:
```
sudo mkdir DisplayVendorID-9e5 && cd DisplayVendorID-9e5 && sudo nano DisplayProductID-62f
```
input bellow and save before reboot to enable Hidpi.You may want to apply wanted Resolution by RDM.app.

## Custom method ——  work on 10.14:
using universal display picture
```bash
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>DisplayHasHardwareBrightnessSmoothing</key>
	<real>1</real>
	<key>DisplayProductID</key>
	<integer>1583</integer>
	<key>DisplayProductName</key>
	<string>Dell 7559 Colors LED Display</string>
	<key>DisplayVendorID</key>
	<integer>2533</integer>
	<key>scale-resolutions</key>
	<array>
		<data>
		AAAPAAAACHAAAAAJAKAAAA==
		</data>
		<data>
		AAANIAAAB2IAAAAJAKAAAA==
		</data>
		<data>
		AAALQAAABlQAAAAJAKAAAA==
		</data>
		<data>
		AAAMgAAABwgAAAAJAKAAAA==
		</data>
		<data>
		AAAKrAAABgAAAAAJAKAAAA==
		</data>
		<data>
		AAAKgAAABegAAAAJAKAAAA==
		</data>
	</array>
</dict>
</plist>
```
## Custom method ——  work on 10.13:
using universal display picture
```bash
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>DisplayHasHardwareBrightnessSmoothing</key>
	<real>1</real>
	<key>DisplayProductID</key>
	<integer>1583</integer>
	<key>DisplayProductName</key>
	<string>Dell 7559 Colors LED Display</string>
	<key>DisplayVendorID</key>
	<integer>2533</integer>
	<key>scale-resolutions</key>
	<array>
		<data>
		AAAPAAAACHAAAAABACAAAA==
		</data>
		<data>
		AAANIAAAB2IAAAABACAAAA==
		</data>
		<data>
		AAALQAAABlQAAAABACAAAA==
		</data>
		<data>
		AAAMgAAABwgAAAABACAAAA==
		</data>
		<data>
		AAAKrAAABgAAAAABACAAAA==
		</data>
		<data>
		AAAKgAAABegAAAABACAAAA==
		</data>
	</array>
</dict>
</plist>
```
## Custom method ——  work on 10.13:
using universal display picture
```bash
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>DisplayHasHardwareBrightnessSmoothing</key>
	<real>1</real>
	<key>DisplayProductID</key>
	<integer>1583</integer>
	<key>DisplayProductName</key>
	<string>Dell 7559 Colors LED Display</string>
	<key>DisplayVendorID</key>
	<integer>2533</integer>
	<key>scale-resolutions</key>
	<array>
		<data>
		AAAPAAAACHAAAAABACAAAA==
		</data>
		<data>
		AAANIAAAB2IAAAABACAAAA==
		</data>
		<data>
		AAALQAAABlQAAAABACAAAA==
		</data>
		<data>
		AAAMgAAABwgAAAABACAAAA==
		</data>
		<data>
		AAAKrAAABgAAAAABACAAAA==
		</data>
		<data>
		AAAKgAAABegAAAABACAAAA==
		</data>
	</array>
</dict>
</plist>
```
### compatible method —— work all 10.12-10.14 :
using Apple Retina display picture
(by the way ,this profile is all version support from 10.11, because piont to defind screen profile).
```ash
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>DisplayHasHardwareBrightnessSmoothing</key>
	<real>1</real>
	<key>DisplayProductID</key>
	<integer>1583</integer>
	<key>DisplayProductName</key>
	<string>Dell 7559 Colors LED Display</string>
	<key>DisplayVendorID</key>
	<integer>2533</integer>
	<key>scale-resolutions</key>
	<array>
		<data>
		AAAPAAAACHAA
		</data>
		<data>
		AAANIAAAB2IA
		</data>
		<data>
		AAALQAAABlQA
		</data>
		<data>
		AAAMgAAABwgA
		</data>
		<data>
		AAAKrAAABgAA
		</data>
		<data>
		AAAKgAAABegA
		</data>
	</array>
	<key>target-default-ppmm</key>
	<real>10.151057399999999</real>
</dict>
</plist>

```
⚠️ NOTICED:
`compatible method` will make the second resolution as default, custom your's as you need.
`compatible method` origin post in pcbeta.com by @triton21, read [his thread](http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1769152&highlight=edid) for more details.
