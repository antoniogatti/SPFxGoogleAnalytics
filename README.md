##Reference
https://www.sharepointvitals.com/blog/google-analytics-for-sharepoint-ultimate-guide/

### Installtion Guide for Dmmies
1. Register you Web Site in Google Analytics: https://analytics.google.com/
2. Run npm i
3. Run gulp build (consider to run gulp clean before)
4. Run gulp bundle --ship
5. Run gulp package-solution --ship

6. Open your SharePoint App catalog and install the .sppkg (\sharepoint\solution\sp-fx-google-analytics.sppkg)
7. Go to the SP site where do you want to active Google Analytics and install the app sp-fx-google-analytics clicking ADD APP in site content
8. Open Terminal in VSCode or PowerShell
9. Run Connect-PnPOnline -url https://<tenant>.sharepoint.com/sites/<site> (if command not available run Install-Module SharePointPnpPowerShellOnoine)
10. Run Add-PnPCustomAction -ClientSideComponentId c430bd95-a1ac-4edd-9e25-7dbf3358062b -Name "Google Analytics for SharePoint" -Title "Google Analytics for SharePoint" -Location ClientSideExtension.ApplicationCustomizer -ClientSideComponentProperties: '{"trackingID":"UA-167399528-1"}'
Note:
a) -ClientSideComponentId is the id value in \dist\id.manifest.json
b) trackingID is the id provided by Google Analytics after the site registration

###!IMPORTANT
The solution package sould be already available in this repository (\sharepoint\solution\sp-fx-google-analytics.sppkg) so you can start the installation from step #6
