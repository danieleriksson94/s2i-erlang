# OpenShift S2I Erlang  Builder

This repository contains the source for building various versions of
Erlang applications as a reproducible Docker image using
[source-to-image](https://github.com/openshift/source-to-image).
The resulting image can be run using [Docker](http://www.docker.com).

For more information about using this image with OpenShift, please see the
official [OpenShift
Documentation](https://docs.openshift.org/latest/architecture/core_concepts/builds_and_image_streams.html#source-build).

## Versions

Erlang versions currently provided are:

* `20.3` (Tags: `20.3`, `20`)
* `21.0` (Tags: `21.0`)
* `21.1` (Tags: `21.1`)
* `21.1` (Tags: `21.3`, `21`, `latest`)

CentOS versions currently supported are:
* CentOS7

## OpenShift Usage

*Currently I have no test-app to test the this builder. It is used as a base for
the elixir builder. PR's to complete the S2I Scripts are welcome!*

<!--
To build an Erlang image:

1. Clone this repo and enter into the directory
  ```
  git clone git@github.com:jshmrtn/s2i-erlang.git
  cd s2i-erlang
  ```

1. Install the example image stream configuration into OpenShift
  ```
  oc create -f imagestream.json
  ```

1. Create the application
  1. WebUI - Navigate to the project, click 'Add to Project' and search for
     the new builder image, select it and populate the fields to create your
     application
  1. Command Line -
    ```
    oc new-app --image-stream=erlang --code https://your.git/repo
    ```
-->

## Local Usage

To build the Erlang Builder image:

* This image is available on DockerHub. To download it run:

```
$ docker pull jshmrtn/s2i-erlang
```

* To build an Erlang builder image from scratch run:

```
$ git clone https://github.com/jshmrtn/s2i-erlang.git
$ cd s2i-erlang/[VERSION]
$ docker build -t jshmrtn/s2i-erlang:[VERSION] .
```
