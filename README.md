# Django starter app for Web App on Linux

# DAILY LOG FOR MARK VOGT (forked & clone this project)

### 2020 50 22 MV: 
- CONTINUED debugging why the LOCALLY-deployed (to Windows10 laptop Docker Engine) WORKS FINE, but CLOUD-deployed (to Container-on-Linux) DOESN'T work 
- THEORY: maybe ALL of the executable files (NOT only the .sh files) must be converted from CRLF ("Windows") to LF ("Linux") formatting? 
- CONVERTED (you can do this by opening each file in VSC and clicking lower-right status bar > CRLF and switching to LF ) ALL files
- RE-DEPLOYED to cloud (multiple steps)
- RESTARTED AzureWebApp "mv3"...
- BROWSED to http://mv3.azurewebsites.net:4000 
- - => NOTHING :-( 
- BROWSED to http://mv3.azurewebsites.net 
- - => WORKING :-) !!!!!!! 
- THEORY (explained by Ian) all of the Docker-related commands and AzureWebApp Services commands issue to :4000 result in any
- requests being sent to http://mv3.azurewebsite.net  being REDIRECTED to http://mv3.azurewebsites.net:4000 and WORKING ! :-) 
- TESTED until CONVINCED entire process is now resulting in a WORKING AzureWebAppServices customDockerContainerImage-based web app ! 
- NEXT: SAVE/COMMIT/PUSH THIS project to github.com and LEAVE IT AS-IS (as a "working template")
- CLONE this project
- MODIFY the CLONED project to actually contain my PEEM "API app" (web service) application
- BUILD/PUSH new customDockerContainerImage to AzureContainerRegistry
- CREATE NEW AzureWebApp "avanade-peem4"  (when working will give http://avanade-peem4.azurewebsites.net)

### 2020 05 21 MV:
- FORKED & CLONED project 
- FOLLOWED steps in this reference: https://docs.microsoft.com/en-us/azure/app-service/containers/tutorial-custom-docker-image
- SLOGGED through some mistakes and Windows/Linux file conversions, but 
- GOT base demo web app working locally on port 4000 :-) 
- CONTINUED with tutorial deploying to AzureContainerRegistry and from there to AzureWebAppServices for hosting an instance...


A simple Python Django application running in a Docker container. The custom image uses port 8000. 

## Setting up custom image for web App on Linux 
- Create a Web App on Linux using CLI or Azure portal
- Configure your web app to custom image 
- Add an App Setting ```WEBSITE_PORT = 8000 ``` for your app 
- Browse your site 
 
# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
