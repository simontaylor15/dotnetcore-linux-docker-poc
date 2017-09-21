[Back to README](README.md)
# Develop an app on Windows and publish & run it in a Docker container hosted on Linux

> _This walkthrough does not rely on having completed the previous walkthroughs, however it is necessary to have access to a Windows machine running Visual Studio 2017 that has connectivity to your Linux environment so that you can copy files between machines (e.g. FTP)_

The app created in this walkthrough will show how to create a web app in Visual Studio (2017) and deploy & run this app within a Docker container hosted Linux. The code for the app can be found in this repo [here](DotNetCoreSimpleApi)

## Compile, Test and Publish the .NET Core Simple API app

1. Clone [this repository](https://github.devops.worldpay.local/sop/dotnetcore-linux-docker-poc) to your Windows machine
2. Open the DotNetCoreSimpleApi project - `DotNetCoreSimpleApi.csproj` - from Visual Studio 2017
3. Compile / Build the project
4. Run the project and test that it is working correctly. Try (from Postman or your browser):
  * http://localhost:5000/api/products
  * http://localhost:5000/api/products/1
5. Next, "Publish" the app.
  1. Right click on the project in Solution Explorer, and select "publish".
  2. Select "Folder" in the next dialog, and select the "Publish" button.
  
You should now have a published web app in the folder /bin/Release/PublishOutput folder. This folder will contain the source code for the app along with all of its dependencies (minus the base .NET Core libraries).

## Transfer the app to your Linux machine

The next step is to transfer the contents of the PublishOutput folder from your windows machine to your Linux box. I used FTP to do this. However you choose to do it, create a folder called "HelloWindows" within the Project directory on your Linux box an copy the content of PublishOutput (along with all subdirectories) into this.

> It doesn't actually matter what you call the target folder on your Linux box for the above step, however the rest of this walkthrough assumes that you named it "HelloWindows"

## Create the Docker image



## Run the app

## Test the app
[Back to README](README.md)
