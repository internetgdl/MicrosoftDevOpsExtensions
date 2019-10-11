Create Microsoft DevOps Extension

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


Firts.

We have to create the folder that we goint to create the projects
install the NPM package manifest
Install the Microsoft VSS Web Extension
Then create the extension manifest
Now create the HUB, is the file that the extensions page will show

TODO: PACKAGE
TODO: Publish