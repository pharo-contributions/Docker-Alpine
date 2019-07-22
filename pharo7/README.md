# Overview

This Dockerfile builds on the Alpine Pharo VM base image, incorporating a
standard Pharo 7.0.3 image. To build the Docker image, put the following
files into the same directory:

- Pharo7.0.3-0-64bit-0903ade.image
- Pharo7.0.3-0-64bit-0903ade.changes
- Pharo7.0-32bit-0903ade.sources 

# Pre-built

A prebuilt Docker image is available as ```pierceng/pharo7-alpine```.

# Running

Run it:

```sh
% sudo docker run --rm --ulimit rtprio=2 pierceng/pharo7-alpine printVersion
[version] 'Pharo7.0.3' 'Pharo-7.0.3+build.158.sha.0903ade8a6c96633f07e0a7f1baa9a5d48cfdf55 (64 Bit)'
```



