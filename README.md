Appcelerator IOS Module - for DocumentPicker
===========================================

Sorry for the spelling mistake in the project name, just noticed it...

![](readme.images/Screen%20Shot.png)

GET STARTED
------------



DOCUMENTATION 
-------------


BUILDING YOUR MODULE
--------------------

Simply run `titanium build --platform <name of platform> --build-type production --dir /path/to/module`.
You can omit the --dir option if your working directory is in the module's project directory.


INSTALL YOUR MODULE
-------------------

Mac OS X
--------
Copy the distribution zip file into the `~/Library/Application Support/Titanium` folder

Linux
-----
Copy the distribution zip file into the `~/.titanium` folder

Windows
-------
Copy the distribution zip file into the `C:\ProgramData\Titanium` folder


REGISTER YOUR MODULE
--------------------

Register your module with your application by editing `tiapp.xml` and adding your module.
Example:

<modules>
	<module version="0.1">com.ci.ios8documemtpicker</module>
</modules>

When you run your project, the compiler will combine your module along with its dependencies
and assets into the application.


USING YOUR MODULE IN CODE
-------------------------

To use your module in code, you will need to require it.

For example,

    var ios8documemtpicker = require('com.ci.ios8documemtpicker');
    Ti.API.info("module is => " + ios8documemtpicker);

    ios8documemtpicker.openDocumentPicker();



Entitlements.plist and your module
----------------------------------
This module requires an `Entitlements.plist` file to be included in the root directory of the `app` folder of the application. The file should look similar to the file below

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<dict>
	  <key>com.apple.developer.icloud-container-identifiers</key>
	  <array>
	    <string>iCloud.[YOUR-APP-BUNDLE-ID]</string>
	  </array>
	  <key>com.apple.developer.icloud-services</key>
	  <array>
			<string>CloudDocuments</string>
			<string>CloudKit</string>
	  </array>
	  <key>com.apple.developer.ubiquity-container-identifiers</key>
	  <array>
	    <string>iCloud.[YOUR-APP-BUNDLE-ID]</string>
	  </array>
	  <key>com.apple.developer.ubiquity-kvstore-identifier</key>
	  <string>[YOUR-TEAM-ID-FROM-XCODE].[YOUR-APP-BUNDLE-ID]</string>
	</dict>
	</plist>

The way I got the proper values was by opening up the application project after depolying the module and confiuring the application for iCloud. The screen to configure iCloud should look similar to this in xCode


![](readme.images/Screenshot%20xcode.png)

Then save the project and open the `appname.entitlements` file in the root of the xcode project directory and the contents should look similar to the xml listed above.
