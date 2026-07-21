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
    * On Dockerhub?
  * `base`: the Dockerfile used throughout the beginning of the case study with various data visualization packages as well as `ggpubr`, but not `patchwork` yet.
    * Image name: `ocs-bio-containers-base`
    * On Dockerhub?
  * `continued-learning`: The Dockerfile adjusted to add `ggrepel` to the `activity` image.
    * Image name: `ocs-bio-containers-cont`
    * On Dockerhub?
