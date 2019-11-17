# gis-administration
## Description
My low-budget homemade administrative tools for ArcGIS Online and Portal. 

Wanted to create administrative tools for typical workflows in Portal/AGOL that don't require Python experience to run.

Disclaimer: I have no background in computer science and am entirely self-taught (been playing around with python for ~ 1 year). As such there may be more efficient or more pythonic ways of writing these tools, but they have been invaluable in helping manage my organisation's AGOL/Portal organisations over the last year.

## Installation
Python and all required packages come installed with ArcGIS Pro. As long as you run these tools from within ArcGIS Pro as they are intended to be used, there should be no additional configuration required.

While I have included all of the individual Python (.py) files, instead of creating your own script tools and having to configure their parameters you can simply download the .tbx file which has these embedded and pre-configured. 

If you would like to run these scripts from an environment other than an ArcGIS Pro script tool, you can make the following changes to do so:
1. Replace the "gis = GIS('pro')" line with another authentication method from the list here https://developers.arcgis.com/python/guide/working-with-different-authentication-schemes/
The most common and safest method being using code like this:
from getpass import getpass
portal_url = 'your_url'
username = 'your_username'
password = getpass() # this prompts the user to input a password, better than hard-coding and storing in the python file
gis = GIS(portal_url, username, password)

2. Replace all instances of "arcpy.AddMessage()" with "print()", replacing the function but keeping the text

3. Replace all instances of "arcpy.GetParameter(x)" and "arcpy.GetParameterAsText(x)" with an appropriate input. For example, for any of the report scripts that require an output filepath as input, simply replace "output_file_path = arcpy.GetParameterAsText(0)" with "output_file_path = r'myfolder\myfile.csv'"

4. Remove "import arcpy" as there shouldn't be any other references to the package once the above changes have been made

## Usage
All of these tools have been designed to run in ArcGIS Pro, and use the active portal in Pro to log in to the "GIS" object from the ArcGIS Api for Python, which supplies the required url and credentials. These will either fail or yield partial results depending on the user type of the account logged in - ideally they should be run from an account with a "User Type" of "Administrator" as this will have full access to the contents of the portal.

### 

## License
