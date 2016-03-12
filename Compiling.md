# Download #

Ensure you have the google plugin for eclipse with AppEngine and GWT 2.5.

do a SVN checkout of the code, it should go to acra-reporter.

Open eclipse, create a workspace (not in acra-reporter)

Do a File->Import

Select acra-reporter folder as the project, it will import.

Right click acra-reporter and select properties, ensure that under Google the following are configured.

App Engine - either use default sdk (1.7.4 currently) or you might need to use specific to select it.

Deployment - application id, you will need to change this later.

Web Toolkit - ensure you have GWT 2.5.0 selected.

Then OK..

Back to the project,

Find the file Configuration.java edit this to suit your defaults.

Then it should build and show no errors, you can also try GWT compile project, it should give no errors.

