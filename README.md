#AutoPkg Recipes for Absolute Manage

Absolute Manage have provided a guide to [install](http://forums.absolute.com/kb.php?a=1062&hilit=autopkg)

For information on AutoPkg please read the [wiki](https://github.com/autopkg/autopkg/wiki/Getting-Started)

To add the packages into Absolute you will require [AbsoluteManageExport](https://github.com/tburgin/AbsoluteManageExport)

##Overrides

Information on recipe overrides can be found [here](https://github.com/autopkg/autopkg/wiki/Recipe-Overrides)

Consider using overrides for some keys, e.g.

* sd\_name\_prefix
* payload\_name\_prefix
* add\_s\_to\_availability\_date

###Example

Firefox override

        <key>Identifier</key>
        <string>local.Future.Absolute.Firefox</string>
        <key>Input</key>
        <dict>
                <key>LOCALE</key>
                <string>en_GB</string>
                <key>NAME</key>
                <string>Firefox</string>
                <key>RELEASE</key>
                <string>latest</string>
                <key>sd_name_prefix</key>
                <string>ABSOLUTE-</string>
                <key>payload_name_prefix</key>
                <string>ABSOLUTE-</string>
                <key>add_s_to_availability_date</key>
                <integer>86400</integer>
        </dict>
        <key>ParentRecipe</key>
        <string>local.amsdpackages.FirefoxESR</string>
