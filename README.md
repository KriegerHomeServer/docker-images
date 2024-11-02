# Home Server Docker Images

[![ci](https://github.com/KriegerHomeServer/docker-images/actions/workflows/build-docker-images.yaml/badge.svg)](https://github.com/KriegerHomeServer/docker-images/actions/workflows/build-docker-images.yaml)

This repository contains release versions of Docker images used in my home server.

### Images

|        Name        |                          Description                           |         Repository         | Latest Tag |
| :----------------: | :------------------------------------------------------------: | :------------------------: | :--------: |
| `Kubernetes Utils` | Image containing various utilities for working with Kubernetes | `teegank/kubernetes-utils` |  `1.0.0`   |

### Example Config

```yaml
# Define metadata for the image
image:
  # The name of the image
  name: example-image
  # The current version of the image
  version: 1.0.0
# Define variables used when building the image
build:
  # The platforms to build the image for
  platforms: linux/amd64,linux/arm64
  # Build arguments to pass when the image is built
  args: |
    SOFTWARE_VERSION=2.0.1
    ANOTHER_SOFTWARE_VERSION=4.0.0
```