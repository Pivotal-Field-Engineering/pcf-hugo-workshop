+++

Categories = ["lab"]
Tags = ["dotnet","microservices","cloudfoundry"]
date = "2017-08-29T07:49:11-04:00"
title = "Lab: Deploying .NET Applications"
weight = 2

+++

### Goal

To deploy a Microsoft Framework .NET Application and a .NET Core Application to Pivotal Cloud Foundry

<!--more-->

Prerequisites
--
1. Install .NET Core 1.x

    [.NET Core](https://www.microsoft.com/net/core)

2. Clone or Download the Dot Net Attendee Source Code

	[Dot Net Environment Viewer:  https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer](https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer)

	##### Get the source code repository app

	<img src="/images/dot-net-framework-git.png" alt="Git style="width: 40%;"/>

	Download the source code. Download as Zip file and save it in local folder

	```bash
	   unzip pcf-dotnet-environment-viewer-master.zip
	```
	##### ---OR---

	Fork and Clone

	[Dot Net Environment Viewer:  https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer](https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer)

	For Linux/Mac:
	```bash
	$git clone https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer.git
	```

	For Windows
	```
	C:\<Some Directory to save code>\> git clone https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer.git
	```
	
3. Clone or Download the Dot Net Core Demo Source Code

	[Dot Net Core Repo:  https://github.com/jennymclaughlin/dotnetcoreCFdemo](https://github.com/jennymclaughlin/dotnetcoreCFdemo)

	##### Get the source code repository app

	<img src="/images/dot-net-core-git.png" alt="Git style="width: 40%;"/>

	Download the source code. Download as Zip file and save it in local folder

	```bash
	   unzip dotnetcoreCFdemo-master.zip
	```
	##### ---OR---

	Fork and Clone

	[Dot Net Core Repo:  https://github.com/jennymclaughlin/dotnetcoreCFdemo](https://github.com/jennymclaughlin/dotnetcoreCFdemo)

	For Linux/Mac:
	```bash
	$git clone https://github.com/jennymclaughlin/dotnetcoreCFdemo.git
	```

	For Windows
	```
	C:\<Some Directory to save code>\> git clone https://github.com/jennymclaughlin/dotnetcoreCFdemo.git
	```


3. Environment Proxy Setup (Optional depending on network configuration)

	If you are connected to a network that requires using a proxy, you'll need to set the appropriate environment variables. In the repository there is a file called *setenv.bat*.

	Open up a terminal/command prompt, change directory to the top level folder and run the setenv.bat file.

	For Mac
	```
	export HTTP_PROXY=<your http proxy>
	export HTTPS_PROXY=<your https proxy>
	```

	For Windows
	```
	set HTTP_PROXY=<your http proxy>
	set HTTPS_PROXY=<your https proxy>

	
Steps
--

In this workshop we are going to follow these steps to deploy .NET Framework and .NET Core applications on Cloud foundry.

***
### Step 1
##### Build the Dot Net Environment Viewer Application
By this point, you should have cloned (or forked, or downloaded) the [DotNetAttendees Repo](https://github.com/Pivotal-Field-Engineering/pcf-dotnet-environment-viewer.git).  Now prepare the application to deploy to Cloud Foundry. 

For this example, we do not need to "build" the application. For other .NET Framework applicaitons, you would publish the project to a specified folder and do the "cf push" from that folder. 

Change into the correct folder. Notice that we are going down two levels to the ViewEnvironment Folder:

Linux/Mac:

    cd pcf-dotnet-environment-viewer/ViewEnvironment


Windows:

    cd pcf-dotnet-environment-viewer\ViewEnvironment


### Step 2
##### Login into Pivotal Cloud Foundry (if necessary)

Each participant will have their own user ids and passwords.  

````
cf login -a https://api.sys.cloud.rick-ross.com --skip-ssl-validation
  Email: myuserid
  Password: ••••••••

  Select a space (or press enter to skip):
  1. development
  2. test
  3. production

  Select any one and stick to that space for the rest of the workshop.

````

Login to the App Console at https://app.cloud.rick-ross.com

<img src="/images/pcf-console.png" alt="PCF App Console" style="width: 70%;"/>


### Step 4
##### Push the app


