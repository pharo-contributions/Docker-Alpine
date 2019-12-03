# Docker-Alpine

Objective: Create the smallest possible Docker image for Pharo for running
headless, batch and server-side applications.

Approach:

- Use [Alpine Linux as base image](https://hub.docker.com/_/alpine) for
  the Pharo VM Docker image. This requires building the Pharo VM to run on
  Alpine Linux. See ```vm.build``` for the howto.

- Reduce the size of the Pharo VM for Alpine Linux, by removing irrelevant built-in
  and external plugins.

- Reduce the size of the application Pharo image, by starting from the
  minimal Pharo image or making use of new bootstrapping techniques.


