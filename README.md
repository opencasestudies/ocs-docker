# ocs-docker

Collection of Docker Images for open case studies

## Repository Function

**Always use a branch to open a pull request to add Dockerfiles to this repository**

The workflow files to support the automatic actions of this repository are in the `.github/workflows` directory:

  * `action.yml`: general action specification for building and pushing an image to DockerHub
  * `manual_dispatch.yml`: action specification for manually building and pushing an image to DockerHub
  * `merge.yml`: **edit to include any new images**
  * `pull_request.yml`: edit to include any new images


## Case Studies Directories

**Always put your Dockerfiles within case study specific directories** and edit the `README` file to describe what each Dockerfile does, how each Dockerfile relates to named images built and pushed to DockerHub, and who the maintainer within the org is.

### `ocs-bio-containers`

Maintainer: `kweav`

  * `activity`: the Dockerfile is adjusted to add a package (`patchwork`) for the data wrangling part of the case study
    * Image name: `ocs-bio-containers-wrangling`
    * On Docker Hub: yes (7/30/26) `bioocs` org, tag `main`
  * `base`: the Dockerfile used throughout the beginning of the case study with various data visualization packages as well as `ggpubr`, but not `patchwork` yet.
    * Image name: `ocs-bio-containers-base`
    * On Docker Hub: yes (7/30/26) `bioocs` org, tag `main` and previously tag `dev` (7/21/26)
  * `continued-learning`: The Dockerfile adjusted to add `ggrepel` to the `activity` image.
    * Image name: `ocs-bio-containers-cont`
    * On Docker Hub: yes (7/30/26) `bioocs` org, tag `main`

### `ocs-bio-spatial-transcriptomics`

Maintainer: `kweav`

* Dockerfile is based off of the `dev` version of `ottr_viz`.
  * Can support OTTR rendering
  * Has visualization packages such as `ggpubr`, `patchwork`, etc. that will be used in this case study.
* Dockerfile includes some dependencies in order to install the packages we especially need for this case study:
  * `GEOquery`
  * `arrow`
  * `rhdf5`
  * `Matrix`
  * `spatialGE`
  * ... [others listed here](https://github.com/opencasestudies/ocs-bio-spatial-transcriptomics/issues/8)
* Image name: `ocs-bio-spatial-transcriptomics`
* On Docker Hub: yes (9/30/26)
  * org: `bioocs`
  * tag: `main`
  * platform: `linux/amd64`
  * manual rather than through the workflows 
