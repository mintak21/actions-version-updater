# actions

## reusable workflows

### docker build and push

build and push registry.
use actions below:

- [qemu](https://github.com/docker/setup-qemu-action)
- [buildx](https://github.com/docker/setup-buildx-action)
- [metadata](https://github.com/docker/metadata-action)
- [build and push](https://github.com/docker/build-push-action)

#### ghcr.io

```yml
jobs:
  build:
    uses: mintak21/actions/.github/workflows/build_ghcr.yml@v0.4.1
    with:
      image: api
```

inputs

##### image

your image name

##### dockerfile

path to Dockerfile

##### tags

image tags
see the table below for default setting:

|event|result|
|:----|:----|
|create tag(vN.N.N)|vN.N.N|
|push branch|{BRANCH_NAME}-{SHA256}|
|pull_request|pr-{PR_NUMBER}|

#### gcr.io

Not yet

#### ecr.io

Not yet

## cron actions

### actions-version-updater

update actions .versions file
runs on every Saturday.

#### target repositories

- [mintak21/terraform](https://github.com/mintak21/terraform)
