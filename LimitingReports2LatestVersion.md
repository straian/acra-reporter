# Introduction #

I find quite often that I get error reports for old versions of the app, where the errors have been fixed - sometimes months ago..

The users, need to be notified when submitting an error report that they are using an old version and that they must upgrade.


# Details #

To start with, the acra-reporter has been modified to return a specific result when a package has been configured to only accept errors for the latest version.

**NOTE** you must be uploading and using mapping files for this to work. (You should always use proguard on your apps).

Download acrasender.zip from the downloads, copy the source to your project and update the package names to whatever you want.

Move activity\_acra\_reporter\_old\_version\_alert.xml to layout.

Add the following strings and customize.

```
    <string name="upgrade">Upgrade</string>
    <string name="acra_old_version_title">Your App - Upgrade</string>
    <string name="acra_old_version_message">You have submitted an error report for an old version of the application. Please upgrade to the latest version to ensure you have the bug fixes.</string>
    <string name="title_activity_acrareporter_old_version_alert">Your App - Old Version</string>`
```
Configure acra to use the new sender.
```
 ACRA.getErrorReporter().setReportSender(new ACRAReporterSender(this));
```

Thats all there is to it - now when the user is attempting a report for the old version (which the version number does not match the most recent mapping file) they will be notified and have a chance to upgrade using the play store.
