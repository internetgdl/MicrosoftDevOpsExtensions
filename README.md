# Create Microsoft DevOps Extension

DevOps is methodology of software development that the focus is the process in that Develop and Operations works together; from the requirements, analysis the requirements, desing the use cases and the test cases, develop the code, test the code, integrate the code test the functionality, release the project and improve the security performance and the project as it self.

The phases of DevOps is:
1. Plan
2. Code 
3. Build
4. Test
5. Release
6. Deploy
7. Operate
8. Monitor

Microsoft DevOps is a tool that help us to plan, integrate the code (using any tool that can use GIT or TFVS), Build, Test, Release and we can monitor some aspects of the components if our project are developed in Azure as IAAS or PAAS.

How we know Microsoft as been opened to all techonologies as we requiere as there a entery world of technologies and it is too much work integrate any model, any technologie or else in the Build and Release module of Microsoft DevOps we can integrate a houndred of extensiones developed by any person that had a requierement and developed a solution.

In this tutorial I'm going to show you how to create and Microsoft DevOps extension using a requirement that I had previously and i resolved with a powershell extensión I'm goint to change the powershell to nodejs.

The requierement was replace the tokens of a appsettings.json for the enviroments vars defined by the configuration of the release enviroment, this because atleast in the xxxxxx version of TFS are imposible to replace the appsettings values for the linux webapps. If you what to read the article the link is here https://github.com/internetgdl/DevOpsCDReplaceTokens

For this requierement we going to create a Release Task

Firts.

We have to create the folder that we goint to create the projects

`mkdir extension` 


initialize the NPM package manifest

`npm init -y`

Install the Microsoft VSS Web Extension

`npm install vss-web-extension-sdk --save`

Then create the extension manifest in a file named as `vss-extension.json` with the follow content

```
{
    "manifestVersion": 1,
    "id": "appsettings-vars-in-artifacts",
    "name": "Replace appsettings variables in artifacts",
    "version": "0.0.4",
    "publisher": "Estrada",
    "targets": [
        {
            "id": "Microsoft.VisualStudio.Services"
        }
    ],    
    "description": "Replace appsettings json variables with environment variables in artifacts.",
    "content": {
        "details": {
            "path": "overview.md"
        }
    },
    "categories": [
        "Azure Pipelines"
    ],
    "icons": {
        "default": "images/extension-icon.png"        
    },
    "files": [
        {
            "path": "buildAndReleaseTask"
        }
    ],
    "contributions": [
        {
            "id": "custom-build-release-task",
            "type": "ms.vss-distributed-task.task",
            "targets": [
                "ms.vss-distributed-task.tasks"
            ],
            "properties": {
                "name": "buildAndReleaseTask"
            }
        }
    ]
} 
```

Now create the HUB, is the file that the extensions page named as `my-hub.html` with the follow content

```
 <!DOCTYPE html>
 <html xmlns="http://www.w3.org/1999/xhtml">
 <head>
	<script src="lib/VSS.SDK.min.js"></script>
	<style>
    	body {
        	background-color: rgb(0, 67, 117);
        	color: white;
        	margin: 10px;    
        	font-family: "Segoe UI VSS (Regular)","-apple-system",BlinkMacSystemFont,"Segoe UI",sans-serif;
    	}
	</style>
	<script type="text/javascript">
    	VSS.init();
    	VSS.ready(function() {
        	document.getElementById("name").innerText = VSS.getWebContext().user.name;
    	});
	</script>
 </head>
 <body>        
	<h1>Hello, <span id="name"></span></h1>
 </body>
 </html>
```



TODO: crearte a publish profile at Marketplace

Create a publish profile in  Marketplace management portal
 https://aka.ms/vsmarketplace-manage

 

TODO: PACKAGE
TODO: Publish