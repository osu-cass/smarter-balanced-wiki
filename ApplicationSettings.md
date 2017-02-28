---
layout: page
title: Application Settings/Build
permalink: /projects/
header: Application Settings and Build Instructions
#Contains Application Setting and BuildApp.md
---


## Application Settings and Configurations
Within the `SmarterBalanced.SampleItems.Web` project, configurations are set 
in the file `appsettings.json`. This file contains all of the configurations and settings 
that are used throughout the application.

Within `appsettings.json`, the `SettingsConfig` object contains configurations 
necessary to start the application, as well as runtime configuration settings.

##### Following is a description of important configurations within this object:

`ContentItemDirectory`: Location of the **Items** directory within the content package. 
Dependent on deployment environment setting (development, staging, production).

`ContentRootDirectory`: Location of the content package. Dependent on deployment 
environment setting (development, staging, production).

`AwsS3Bucket`: AWS S3 bucket that contains the content package. Required for 
the diagnostic status feature.

`AwsRegion`: AWS region. Required for the diagnostic status feature.

`ItemViewerServiceURL`: Base URL for itemviewerservice, which renders the test question items. 
URL is used to display an iframe of each item.

`AwsClusterName`: Name of AWS cluster. Required for the diagnostic status feature.

`StatusUrl`: Diagnostic status URL for local diagnostic status. Required for the diagnostic status feature.

`AccommodationsXMLPath`: Location of the accessibility configurations XML document.

`InteractionTypesXMLPath`: Location of the interaction types configuration XML document.

`ClaimsXMLPath`: Location of the claims configuration XML document.

Additionally, the `RubricPlaceHolderText` object contains strings that are filtered
out of item 

## Build Instructions
Sampleitems Website requires content before running. 

There is a two-step process using docker. The base app without content needs 
to be created as a docker image called code. Then we combine the code image 
with the content package using another dockerfile. 

### Before starting build
Locate the dockerfile.stage and dockerfile.prod files
from github repo, navigate to deployScripts

### Using a previous docker code image
To build a docker image for sample items website code base (without content) see Building from scratch

#### Docker
1. Navigate to directory containing dockerfiles
2. Get docker code repo for stage/prod, run `docker pull reponame:{tag}`
    1. Example stage: run `docker pull xxx.dkr.ecr.us-west-2.amazonaws.com/sampleitemscode:stage`
    2. Example producation: run `docker pull xxx.dkr.ecr.us-west-2.amazonaws.com/sampleitemscode:prod`
3. Docker tag code, run `docker tag reponame:{tag} sampleitemscode:{tag}`
    1. Example stage: run `docker tag xxx.dkr.ecr.us-west-2.amazonaws.com/sampleitemscode:stage sampleitemscode:stage`
    2. Example production: run `docker pull xxx.dkr.ecr.us-west-2.amazonaws.com/sampleitemscode:prod sampleitemscode:prod`
4. place content within deployScripts directory
    1. Content needs to be unzipped
    2. content directory root level needs Items directory
5. Docker build, run `docker build -t sampleitemsapp:{tag} -f Dockerfile.{tag} .`
    1. Example stage: run `docker build -t sampleitemsapp:stage -f Dockerfile.stage .`
    2. Example production: run `docker build -t sampleitemsapp:prod -f Dockerfile.prod .`
6. Docker Run app , run `docker exec -it -p 8012:80 sampleitemsapp:{tag}`
    1. Example stage: run `docker exec -it -p 8012:80 sampleitemsapp:stage`
    2. Example production: run `docker exec -it -p 8012:80 sampleitemsapp:prod`
7. Go to [localhost:8012](http://localhost:8012)
8. point to docker

### Building from scratch
#### Dependencies
1. See [Project Dependencies](#internal-dependencies)
2. Install Nodejs and npm

#### Dotnet build and Publish
1. `cd SampleItemsWebsite\SmarterBalanced.SampleItems`
2. `dotnet restore`
3. `cd src\SmarterBalanced.SampleItems.Web`
4. `npm install`
5. `grunt all`
6. `dotnet publish -o ../../publish`
7. `cd ../../publish`

#### Docker build
1. Go to the publish directory containing the dockerfile
2. Build app, run `docker build -t sampleitemscode:{tag}`
    1. Example stage: run `docker build -t sampleitemscode:stage`
    2. Example producation: run `docker build -t sampleitemscode:prod`

#### Deploy Sample Items app
1. see [Publish Docker](#publish-docker-to-aws)