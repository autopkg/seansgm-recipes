##AutoPkg Recipes for FileWave & LANrev

For information on AutoPkg please read the [wiki](https://github.com/autopkg/autopkg/wiki/Getting-Started)

## For Anyone New
[LANrevImporter](https://github.com/jbaker10/LANrevImporter) is required to upload packages into your LANrev database and "LANrev Admin.app" needs to be running and signed in with a user who has permissions to add payloads and packages.  See the LANrevImporter page for more details.

[FWTools](https://github.com/autopkg/filewave) are required to upload packages into your FileWave database.  You will also find some FileWave recipes and the guide to get you started with FileWave

## LANrev Note

Due to LANrev's imminent end of life, it is highly unlikely I will make any chanage to the LANrev recipes anymore.
FileWave recipes will now be offered instead

## Recipes

All these recipes require a parent.  Look at the ParentRecipe key in the file.  For example, Firefox.LANrev.recipe

        <key>ParentRecipe</key>
        <string>com.github.autopkg.pkg.Firefox_EN</string>
        
Alternatively, you can get parent info running:

        autopkg info Firefox.LANrev
        
which in turn will show all parents

    Recipe file path:    /Volumes/DATA/autopkg/Recipes/LANrev/Firefox.LANrev.recipe
    Parent recipe(s):    /Volumes/DATA/autopkg/RecipeRepos/com.github.autopkg.recipes/Mozilla/Firefox.pkg.recipe
                         /Volumes/DATA/autopkg/RecipeRepos/com.github.autopkg.recipes/Mozilla/Firefox.download.recipe

##Overrides

Information on recipe overrides can be found [here](https://github.com/autopkg/autopkg/wiki/Recipe-Overrides)

Consider using overrides for some keys, e.g.

* sd\_name\_prefix
* payload\_name\_prefix
* add\_s\_to\_availability\_date

###Example

Firefox override

        <key>Identifier</key>
        <string>local.Override.LANrev.Firefox</string>
        <key>Input</key>
        <dict>
                <key>LOCALE</key>
                <string>en_GB</string>
                <key>NAME</key>
                <string>Firefox</string>
                <key>RELEASE</key>
                <string>latest</string>
                <key>sd_name_prefix</key>
                <string>LANrev-</string>
                <key>payload_name_prefix</key>
                <string>LANrev-</string>
                <key>add_s_to_availability_date</key>
                <integer>86400</integer>
        </dict>
        <key>ParentRecipe</key>
        <string>local.amsdpackages.FirefoxESR</string>

autopkg info will also show any overrides if there are any

        autopkg info Firefox.LANrev.Override


    Input values: 
        LOCALE = "en_GB";
        NAME = Firefox;
        RELEASE = latest;
        "add_s_to_availability_date" = 86400;
        "payload_name_prefix" = "LANrev-";
        "sd_name_prefix" = "LANrev-";
