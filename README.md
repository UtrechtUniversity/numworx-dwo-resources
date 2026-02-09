# numworx-dwo-resources

All static resources for DWO services

## Introduction

This git repository builds the static webservice, which can uses as is, or as
backend of a Content Delivery Network, like AWS Cloudfront of Azure FrontDoor.


## Prerequisites
The maven build uses artifacts from the following repositories
- numworx-dwo-author
- numworx-gwt-widgets
- numworx-dwo-project

Build them first.

## Contents 

### Folder structure

This project is organized as follows:
- CDSDocker. Build the tomcat static webserver container
- cds-war. All additional resources for the authoring environment NumworxAuthor in a war.
- apps-war. All additional resources for the web platform in a war.
- profile-styles. All css resources that implements the skins for e.g. Wiskunde-Actief and Co-Teach. 

### Building 

Everything is built through maven: `mvn install -Pgithub`

**Note**
- To push to a docker registry, please login first.
- Enable multiplatform builds with buildx.
- GitHub artifacts need authenticated access. Define the GITHUB_TOKEN environment variable with your *GITHUB_TOKEN*.


## Usage

The main artifact is the container image **ghcr.io/utrechtuniversity/numworx-dwo-resources/cds**:*version* for linux/arm64 and linux/amd64 environments

To run in a docker environment:

    docker run -d -P 8080:8080 ghcr.io/utrechtuniversity/numworx-dwo-resources/cds:version

In the git repository numworx-dwo-setup this image is run in a kubernetes cluster.

## License

With an open-source license, you grant permission to use your work.
The most common open-source licenses are MIT, GPL3, and Apache 2.0.
Choose a license that aligns with your goals for your code.

For example:

> This work is licensed under the MIT License.

## Contact 
[Wim van Velthoven](mailto:w.p.g.vanvelthoven@uu.nl)
