# drone-telegram

![logo](./images/logo.png)

[![GoDoc](https://godoc.org/github.com/New-Dev3/drone-tele?status.svg)](https://godoc.org/github.com/New-Dev3/drone-tele)
[![Build Status](https://cloud.drone.io/api/badges/New-Dev3/drone-tele/status.svg)](https://cloud.drone.io/New-Dev3/drone-tele)
[![Build status](https://ci.appveyor.com/api/projects/status/cm4l9udn8ywkif42?svg=true)](https://ci.appveyor.com/project/New-Dev3/drone-tele-cd47y)
[![codecov](https://codecov.io/gh/New-Dev3/drone-tele/branch/master/graph/badge.svg)](https://codecov.io/gh/New-Dev3/drone-tele)
[![Go Report Card](https://goreportcard.com/badge/github.com/New-Dev3/drone-tele)](https://goreportcard.com/report/github.com/New-Dev3/drone-tele)
[![Docker Pulls](https://img.shields.io/docker/pulls/New-Dev3/drone-tele.svg)](https://hub.docker.com/r/New-Dev3/drone-tele/)

[Drone](https://github.com/drone/drone) plugin for sending telegram notifications. For the usage
information and a listing of the available options please take a look at [the docs](http://plugins.drone.io/appleboy/drone-telegram/).

## Feature

* [x] Send with Text Message. (`markdown` or `html` format)
* [x] Send with New Photo.
* [x] Send with New Document.
* [x] Send with New Audio.
* [x] Send with New Voice.
* [x] Send with New Location.
* [x] Send with New Venue.
* [x] Send with New Video.
* [x] Send with New Sticker.

## Build or Download a binary

The pre-compiled binaries can be downloaded from [release page](https://github.com/New-Dev3/drone-tele/releases). Support the following OS type.

* Windows amd64/386
* Linux arm/amd64/386
* Darwin amd64/386

With `Go` installed

```sh
go get -u -v github.com/New-Dev3/drone-tele
```

or build the binary with the following command:

```sh
export GOOS=linux
export GOARCH=amd64
export CGO_ENABLED=0
export GO111MODULE=on

go test -cover ./...

go build -v -a -tags netgo -o release/linux/amd64/drone-tele .
```

## Testing

Test the package with the following command:

```sh
make test
```

## Usage

Execute from the working directory:

```sh
docker run --rm \
  -e PLUGIN_TOKEN=xxxxxxx \
  -e PLUGIN_TO=xxxxxxx \
  -e PLUGIN_MESSAGE=test \
  -e PLUGIN_MESSAGE_FILE=testmessage.md \  
  -e PLUGIN_PHOTO=tests/github.png \
  -e PLUGIN_DOCUMENT=tests/gophercolor.png \
  -e PLUGIN_STICKER=tests/github-logo.png \
  -e PLUGIN_AUDIO=tests/audio.mp3 \
  -e PLUGIN_VOICE=tests/voice.ogg \
  -e PLUGIN_LOCATION="24.9163213 121.1424972" \
  -e PLUGIN_VENUE="24.9163213 121.1424972 title address" \
  -e PLUGIN_VIDEO=tests/video.mp4 \
  -e PLUGIN_DEBUG=true \
  -e PLUGIN_ONLY_MATCH_EMAIL=false \
  -e PLUGIN_FORMAT=markdown \
  -e DRONE_REPO_OWNER=appleboy \
  -e DRONE_REPO_NAME=go-hello \
  -e DRONE_COMMIT_SHA=e5e82b5eb3737205c25955dcc3dcacc839b7be52 \
  -e DRONE_COMMIT_BRANCH=master \
  -e DRONE_COMMIT_LINK=https://github.com/appleboy/go-hello/compare/master... \
  -e DRONE_COMMIT_AUTHOR=New-Dev3 \
  -e DRONE_COMMIT_AUTHOR_EMAIL=New-Dev3@gmail.com \
  -e DRONE_BUILD_NUMBER=1 \
  -e DRONE_BUILD_STATUS=success \
  -e DRONE_BUILD_LINK=http://github.com/appleboy/go-hello \
  -e DRONE_TAG=1.0.0 \
  -e DRONE_JOB_STARTED=1477550550 \
  -e DRONE_JOB_FINISHED=1477550750 \
  -v $(pwd):$(pwd) \
  -w $(pwd) \
  New-Dev3/drone-tele
```

Load all environments from file.

```bash
docker run --rm \
  -e PLUGIN_ENV_FILE=your_env_file_path \
  -v $(pwd):$(pwd) \
  -w $(pwd) \
  New-Dev3/drone-tele
```
## ???? Credits
>> [Apple Boy](https://github.com/appleboy) - He is The Original Repo Master