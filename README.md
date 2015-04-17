#AutoPkg Absolute Manage Recipes


Absolute Manage has a page explaining configuration [here](http://forums.absolute.com/kb.php?a=1062&hilit=autopkg)

For more information on AutoPkg check out the [wiki](https://github.com/autopkg/autopkg.wiki.git)

To upload to Absolute Manage you will require [AbsoluteManageExport](https://github.com/tburgin/AbsoluteManageExport)

Overrides
----

Consider using [recipe overrides](https://github.com/autopkg/autopkg.wiki.git) for some keys:

* sd\_name\_prefix
* payload\_name\_prefix
* add\_s\_to\_availability\_date (seconds added or subtracted to current time to adjust availability date)

###Example

Firefox override.

        <key>Identifier</key>
        <string>local.Override.Absolute.Firefox</string>
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
