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
* `21.0` (Tags: `21.0`, `21`, `latest`)

CentOS versions currently supported are:
* CentOS7

## Openshift Usage

*Currently I have no test-app to test the this builder. It is used as a base for
the elixir builder. PR's to complete the S2I Scripts are welcome!*

## Local Usage

*Currently I have no test-app to test the this builder. It is used as a base for
the elixir builder. PR's to complete the S2I Scripts are welcome!*
