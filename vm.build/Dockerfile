FROM alpine:3.12 as build
RUN apk add --no-cache --update build-base git bash perl curl linux-headers libexecinfo-dev util-linux-dev cmake clang clang-dev
WORKDIR /src
RUN git clone https://github.com/PierceNg/opensmalltalk-vm --depth 1 -b pierce_alpine_839a5ca .  \
  && scripts/updateSCCSVersions
RUN cd build.linux64x64/pharo.cog.spur.minheadless/build \
  && echo y | ./mvm
# mvm is expensive. Do it as one RUN so that the output is cached by Docker.
# Additional customizations go below.
RUN cd /src/products/ph64mincogspur64linuxht \
  && rm libPharoVMCore.a \
  && strip * \
  && true 

FROM alpine:3.12
RUN apk add --no-cache --update libexecinfo \
  &&  mkdir -p /pkg/vm
COPY --from=build /src/products/ph64mincogspur64linuxht /pkg/vm

