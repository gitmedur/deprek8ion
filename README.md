# Deprek8ion 🕵️‍

[![CircleCI](https://circleci.com/gh/swade1987/deprek8ion.svg?style=svg)](https://circleci.com/gh/swade1987/deprek8ion)

A set of rego policies to monitor Kubernetes APIs deprecations.

The Kubernetes API deprecations can be found using <https://relnotes.k8s.io/?markdown=deprecated>.

## Docker image

The docker container contains the most recent version of [conftest](https://github.com/instrumenta/conftest) as well as the policies at `/policies`.

Image tags can be found at [https://eu.gcr.io/swade1987/deprek8ion](https://eu.gcr.io/swade1987/deprek8ion)

## Example usage

An example of how to use the docker container can be seen below:

```sh
docker run --rm --name demo -v $(pwd)/demo:/demo eu.gcr.io/swade1987/deprek8ion:1.1.17 /demo/ingress.yaml
```

Or directly pipe some resources into the container:

```sh
cat ./demo/ingress.yaml | docker run --rm -i eu.gcr.io/swade1987/deprek8ion:1.1.17 -
```
