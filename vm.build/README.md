# Purpose

This Dockerfile builds the Pharo ```pharo.cog.spur.minheadless``` VM on
Alpine Linux within Docker. This allows one to build said VM without having
to first create an Alpine Linux installation such as through VirtualBox.

# How It Works

This is a multi-stage Dockerfile. The Pharo VM is built in an Alpine Linux
'build' container. Then the VM files are copied into a fresh Alpine Linux
Docker image. The resulting Pharo VM Docker image is ~14 MB.

# How To Use

The output Docker image contains the Pharo VM only and is not runnable by
itself. It is intended to be used as a base to build your own Docker image
containing your application-specific Pharo image.


