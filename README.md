xorg.conf
=====
Section "ServerLayout"
	Identifier     "X.org Configured"
	Screen      0  "Screen0" 0 0
	Screen      1  "Screen1" RightOf "Screen0"
	Screen      2  "Screen2" RightOf "Screen1"
	InputDevice    "Mouse0" "CorePointer"
	InputDevice    "Keyboard0" "CoreKeyboard"
EndSection

Section "Files"
	ModulePath   "/usr/lib/xorg/modules"
	FontPath     "/usr/share/fonts/X11/misc"
	FontPath     "/usr/share/fonts/X11/cyrillic"
	FontPath     "/usr/share/fonts/X11/100dpi/:unscaled"
	FontPath     "/usr/share/fonts/X11/75dpi/:unscaled"
	FontPath     "/usr/share/fonts/X11/Type1"
	FontPath     "/usr/share/fonts/X11/100dpi"
	FontPath     "/usr/share/fonts/X11/75dpi"
	FontPath     "/var/lib/defoma/x-ttcidfont-conf.d/dirs/TrueType"
	FontPath     "built-ins"
EndSection

Section "Module"
	Load  "record"
	Load  "dbe"
	Load  "glx"
	Load  "dri"
	Load  "extmod"
	Load  "dri2"
EndSection

Section "InputDevice"
	Identifier  "Keyboard0"
	Driver      "kbd"
EndSection

Section "InputDevice"
	Identifier  "Mouse0"
	Driver      "mouse"
	Option	    "Protocol" "auto"
	Option	    "Device" "/dev/input/mice"
	Option	    "ZAxisMapping" "4 5 6 7"
EndSection

Section "Monitor"
	Identifier   "Monitor0"
	VendorName   "Monitor Vendor"
	ModelName    "Monitor Model"
EndSection

Section "Monitor"
	Identifier   "Monitor1"
	VendorName   "Monitor Vendor"
	ModelName    "Monitor Model"
EndSection

Section "Monitor"
	Identifier   "Monitor2"
	VendorName   "Monitor Vendor"
	ModelName    "Monitor Model"
EndSection

Section "Device"
        ### Available Driver options are:-
        ### Values: <i>: integer, <f>: float, <bool>: "True"/"False",
        ### <string>: "String", <freq>: "<f> Hz/kHz/MHz",
        ### <percent>: "<f>%"
        ### [arg]: arg optional
        #Option     "NoAccel"            	# [<bool>]
        #Option     "AccelMethod"        	# <str>
        #Option     "HWCursor"           	# [<bool>]
        #Option     "SWCursor"           	# [<bool>]
        #Option     "ShadowFB"           	# [<bool>]
        #Option     "Rotate"             	# [<str>]
        #Option     "UseBIOS"            	# [<bool>]
        #Option     "LCDClock"           	# <freq>
        #Option     "ShadowStatus"       	# [<bool>]
        #Option     "CrtOnly"            	# [<bool>]
        #Option     "TvOn"               	# [<bool>]
        #Option     "PAL"                	# [<bool>]
        #Option     "ForceInit"          	# [<bool>]
        #Option     "Overlay"            	# [<str>]
        #Option     "TransparencyKey"    	# [<str>]
        #Option     "ForceInit"          	# [<bool>]
        #Option     "DisableXVMC"        	# [<bool>]
        #Option     "DisableTile"        	# [<bool>]
        #Option     "DisableCOB"         	# [<bool>]
        #Option     "BCIforXv"           	# [<bool>]
        #Option     "DVI"                	# [<bool>]
        #Option     "IgnoreEDID"         	# [<bool>]
        #Option     "BusType"            	# [<str>]
        #Option     "DmaType"            	# [<str>]
        #Option     "DmaMode"            	# [<str>]
        #Option     "AGPMode"            	# <i>
        #Option     "AGPSize"            	# <i>
        #Option     "DRI"                	# [<bool>]
        #Option     "AGPforXv"           	# [<bool>]
	Identifier  "Card0"
#	Driver      "savage"
Driver	"s3"
	BusID       "PCI:1:0:0"
EndSection

Section "Device"
        ### Available Driver options are:-
        ### Values: <i>: integer, <f>: float, <bool>: "True"/"False",
        ### <string>: "String", <freq>: "<f> Hz/kHz/MHz",
        ### <percent>: "<f>%"
        ### [arg]: arg optional
        #Option     "ShadowFB"           	# [<bool>]
        #Option     "Rotate"             	# <str>
        #Option     "fbdev"              	# <str>
        #Option     "debug"              	# [<bool>]
	Identifier  "Card1"
	Driver      "fbdev"
	BusID       "PCI:1:0:0"
EndSection

Section "Device"
        ### Available Driver options are:-
        ### Values: <i>: integer, <f>: float, <bool>: "True"/"False",
        ### <string>: "String", <freq>: "<f> Hz/kHz/MHz",
        ### <percent>: "<f>%"
        ### [arg]: arg optional
        #Option     "ShadowFB"           	# [<bool>]
        #Option     "DefaultRefresh"     	# [<bool>]
        #Option     "ModeSetClearScreen" 	# [<bool>]
	Identifier  "Card2"
	Driver      "vesa"
	BusID       "PCI:1:0:0"
EndSection

Section "Screen"
	Identifier "Screen0"
	Device     "Card0"
	Monitor    "Monitor0"
	SubSection "Display"
		Viewport   0 0
		Depth     1
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     4
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     8
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     15
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     16
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     24
	EndSubSection
EndSection

Section "Screen"
	Identifier "Screen1"
	Device     "Card1"
	Monitor    "Monitor1"
	SubSection "Display"
		Viewport   0 0
		Depth     1
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     4
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     8
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     15
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     16
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     24
	EndSubSection
EndSection

Section "Screen"
	Identifier "Screen2"
	Device     "Card2"
	Monitor    "Monitor2"
	SubSection "Display"
		Viewport   0 0
		Depth     1
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     4
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     8
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     15
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     16
	EndSubSection
	SubSection "Display"
		Viewport   0 0
		Depth     24
	EndSubSection
EndSection

