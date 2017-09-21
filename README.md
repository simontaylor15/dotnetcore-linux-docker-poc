# Cross Platform .NET Development using Linux and Docker

## Introduction

The purpose of this repo is to demonstrate:

* How to develop and run a .NET Core application on Linux
* How to build and run a Docker image hosted on Linux which contains a .NET Core app
* How to build an application on Windows using Visual Studio (2017) and then publish & run this app within a Docker container hosted on Linux

## Prerequisites

1. Access to a Linux VM / environment. I used version 14.05.05 of the Ubuntu distro but the steps described with work with other distros too
2. Docker installed. I used version 1.13.1 of both client & server
3. The .NET Core SDK installed. I used version version 1.0.4. (Version 2.0.0 is available at the time of writing this page but is not in LTS)
4. Access to a Windows machine / VM with Visual Studio 2017 installed (this requirement is only needed if you wish to undertake the last walkthrough below)

## Walkthroughs

1. [Develop & run your first .NET Core application on Linux](HelloWorld.md)
2. [Create a docker image containing a .NET Core application hosted on Linux](HelloDocker.md)
3. [Develop an app on Windows and publish & run it in a Docker container hosted on Linux](HelloWindows.md)
