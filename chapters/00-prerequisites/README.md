# Prerequisites

Prepare your computer before the workshop, so you don't wait for installs and downloads during it.

## What you need

### Workshop repository

Clone this repository and go to its root.
All commands in the workshop run from there.

```shell
git clone https://github.com/datamole-ai/openshell-workshop.git
cd openshell-workshop
```

### Docker

Check that your Docker is version 28.0 or later.

```shell
docker --version
```

### OpenShell

Check that your OpenShell is version 0.1.2.

```shell
openshell --version
```

If OpenShell isn't installed, install it with the official script ([docs](https://docs.nvidia.com/openshell/latest/about/installation)).
It detects your distribution and installs a Debian or RPM package.

```shell
curl -LsSf https://raw.githubusercontent.com/NVIDIA/OpenShell/main/install.sh | sh
```

Check that the CLI can reach the gateway.

```shell
openshell status
```

### Base image

Pull the image that the workshop image is built on.

```shell
docker pull nvcr.io/nvidia/base/ubuntu:24.04
```

### GitHub repository

Pick a repository that you can push to, ideally private.
You will create a token with access only to this repository.

If you don't have one to use, fork [datamole-ai/openshell-workshop](https://github.com/datamole-ai/openshell-workshop).

## Next chapter

[Introduction](../01-intro/README.md)
