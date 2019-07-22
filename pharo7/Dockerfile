FROM pierceng/pharovm-alpine:1ea727f
WORKDIR /pkg/image
COPY Pharo7.0.3-0-64bit-0903ade.image pharo703.image
COPY Pharo7.0.3-0-64bit-0903ade.changes pharo703.changes
COPY Pharo7.0-32bit-0903ade.sources Pharo7.0-32bit-0903ade.sources 
RUN addgroup -g 1099 pharoapp \
  && adduser -D -u 1099 -G pharoapp -h /home/pharoapp pharoapp \
  && chown -R pharoapp:pharoapp /pkg/image \
  && chown root:root /pkg/image/Pharo7.0-32bit-0903ade.sources 
USER pharoapp:pharoapp
ENV LD_LIBRARY_PATH /pkg/vm
ENTRYPOINT ["/pkg/vm/pharo", "-headless", "pharo703.image"]
VOLUME /pkg/image
