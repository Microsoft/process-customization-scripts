Process Customization Scripts
===================


These scripts are designed to automate the exporting and importing of your TFS process templates.

----------


Export
-------------

The ExportProjectsTemplate.ps1 will connect to your TFS or VSTS project and extract the process template.
> **Folder Structure**

> Root Folder
> --- Default_EmptyTemplate
> --- Exported Templates
> --- ExportProjectTemplate.ps1
#### <i class="icon-folder"></i> Default_EmptyTemplate

The folder contains series of files and folders that are needed when extracting the process template from the project. Don't change anything in this folder.
#### <i class="icon-folder"></i> ExportedTemplates

This is where your process template will be stored after the script run is completed. The PowerShell script specifically looks for this folder. 

#### <i class="icon-file"></i> ExportProjectTemplate.ps1

PowerShell script that extracts the process from the project and saves it into the <i class="icon-folder"></i> **ExportedTemplates** folder

Syntax
```
./ExportProjectTemplate.ps1 "collection" "projectname" -Force
```

Example
```
.\ExportProjectTemplate.ps1 "http://myServer/tfs/DefaultCollection" "foo" -Force
```
> **Note:** You will need to run the ExportProjectTemplate.ps1 script for each project 

-------------

Import
-------------------

ConformProject.ps1 will take a defined process template that is on your local machine and apply it, in full, to a specified project. Typical use case for this is to update to the most recent OOB Agile, Scrum, or CMMI template. You may also be a large organization that has made a change to process and need to apply it many projects within your collection.

#### <i class="icon-folder"></i>Process Template (Agile, Scrum, Customized)
You will need the entire process template downloaded in a location you can get access it via your desktop. When executing the script you supply the full path to this folder 

#### <i class="icon-file"></i> ConformProject.ps1

PowerShell script that runs a takes a process template path and runs a series of witadmin commands to apply it to a supplied project.

Syntax
```
./ConformProject.ps1 "collection" "projectname" "templatepath"
```

Example
```
./ConformProject.ps1 "http://myServer/tfs/DefaultCollection" "foo" "c:\folder\agile"
```

Support
-------------------
Contact vsocustpt@microsoft.com with questions or issues
