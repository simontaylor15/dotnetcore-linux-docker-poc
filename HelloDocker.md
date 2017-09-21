[Back to README](README.md)
# Creating & running a .NET Core docker image hosted on Linux
> _This walkthrough assumes you have completed the previous steps described [here](HelloWorld.md)_

## Publish the .NET Core application

To create the Docker image, we must first publish the .NET Core app that we created in the previous step. This places all of the files required by your app into a folder for it to be deployed.

> _Note that there are two deployment types for .NET Core: Self Contained (SCD) and Framework Dependent (FDD). This walkthrough demonstrates the 2nd type (FDD). We will be createing a Docker image from the base .NET Core framework so we do not need to inlucde this with our deployment._

From the HelloLinux folder we created in the previous walkthough, type:

```
dotnet publish -o out
```

The default when publishing a .NET Core app is for it to be Framework Dependent. The `-o` switch is used to specify which folder to place the published app to.

## Create a Dockerfile 

Now that we have published our application, we can create the Docker image from which our container will be based. Our Docker image will be based on the official base .NET Core Docker images from Microsoft which are available on [Docker Hub](https://hub.docker.com/r/microsoft.dotnet). Microsoft have made several Docker images available. In our case we will be using just the runtime image (An image containing the SDK is also available but we will not be using that in this walkthrough). To ensure the latest .NET core runtime image is available, type the following:

```
docker pull microsoft/dotnet:runtime
```

> You can list the Docker images available on your machine by typing `docker images`

To create the Docker image containing our .NET Core Hello World app, first create a file called `Dockerfile` within the folder containing the source code for our application (HelloLinux). Open this file in an editor (I used `nano` - i.e. `nano Dockerfile`) and add the following lines to the file:

```
FROM microsoft/dotnet:runtime
COPY out /app
WORKDIR app

ENTRYPOINT ["dotnet", "HelloLinux.dll"]
```

The lines above tell Docker to create a new image, and base on the .NET Core runtime image available from Microsoft. The files from our published app are then copied into this image, and finally we tell the Docker run time what to do when the Container runs. 

> The above Dockerfile is available in this repo [here]

The next step is to create a new Docker image from this file.

## Build the Dockerfile into a Docker image

```
docker build . -t hellolinux
```

The above command will build the Dockerfile we created into a Docker image. You should now see the new image by listing out the Docker images by typing `docker images`. The -t switch gives the image a name which we can refer to when we want to run the container; in this case "hellolinux"

## Run the Docker container

To run a Docker container bfrom the image we have created, type the following:

```
docker run -d hellolinux
```

Docker containers do not, by default, remove themselves when they have finish - using the -d switch will remove the container once it has completed.

> _Note that the runtime included in the .NET Core SDK used to create our published app must match the runtime image that we downloaded from Dockerhub. If these 2 differ then you your app will not run as expected._

[Back to README](README.md)
