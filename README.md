#AutoPkg Recipes for LANrev (formerly Absolute Manage)

For information on AutoPkg please read the [wiki](https://github.com/autopkg/autopkg/wiki/Getting-Started)

~~Absolute Manage have provided a guide to [install](http://forums.absolute.com/kb.php?a=1062&hilit=autopkg)~~

## For Anyone New
[LANrevImporter](https://github.com/jbaker10/LANrevImporter) is required to upload packages into your LANrev database and "LANrev Admin.app" needs to be running and signed in with a user who has permissions to add payloads and packages.  See the LANrevImporter page for more details.

## For Those Transitioning

You may need to wait if you are using [Autopkgr](https://github.com/lindegroup/autopkgr).  Hopefully there will be an update in V1.4

The Absolute recipes have been duplicated to allow for the transition to LANrev.  Any future changes required will only be reflected in the newer LANrev recipes.  Please adopt these newer LANrev recipes.  Although the Absolute recipes are still in this repo, they will be deleted at some point.  Please ensure you change any override recipes to point to each new ParentRecipe.

[AbsoluteManageExport](https://github.com/tburgin/AbsoluteManageExport) has been replaced with [LANrevImporter](https://github.com/jbaker10/LANrevImporter).

Although you can continue to use AbsoluteManageExport, new features will only be added to LANrevImporter and if there is any deprecated code in AbsoluteManageExport, it will not be updated.

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
