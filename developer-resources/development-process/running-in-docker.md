---
description: How to run Nuclear in a Docker container
---

# Running in Docker

It's also possible to run the development environment using docker containers, but this should be considered experimental.

You will need docker and docker-compose. You need to allow the root user to connect to X11 display, and then you can run docker-compose:

```text
$ xhost SI:localuser:root
$ sudo docker-compose up dev
```

