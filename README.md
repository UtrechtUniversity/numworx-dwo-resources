# numworx-dwo-resources

All static resources for DWO services

## Introduction

This git repository builds the static webservice, which can be used as is, or as a
backend of a Content Delivery Network, like AWS Cloudfront of Azure FrontDoor.
The CDN must implement CORS headers!


## Prerequisites
The maven build uses artifacts from the following repositories
- numworx-dwo-author
- numworx-gwt-widgets
- numworx-dwo-project
- numworx-dwo-runner

Build them first.

## Contents 

### Folder structure

This project is organized as follows:
- CDSDocker. Build the tomcat static webserver container image
- cds-war. All additional resources for the authoring environment NumworxAuthor in a war. Combines resources-war and jars-war.
- jars-war. All jars needed for NumworxAuthor
- resources-war. All resources (images, properties, fonts, styling) for NumworxAuthor
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

    docker run -d -p 8080:8080 --name cds ghcr.io/utrechtuniversity/numworx-dwo-resources/cds:version

In the git repository numworx-dwo-setup this image is run in a kubernetes cluster.

## License

This work is licensed under the GNU General Public License version 3.
Copyright © 2026, Utrecht University, all rights reserved.

## Contact 
[Wim van Velthoven](mailto:w.p.g.vanvelthoven@uu.nl)
