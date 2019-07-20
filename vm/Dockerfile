FROM alpine:3.10
RUN mkdir -p /pkg/vm
COPY pharo7vm /pkg/vm
ENTRYPOINT ["/pkg/vm/gofaro"]
