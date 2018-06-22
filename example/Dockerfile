FROM ytaka23/stack-ghcjs:lts-7.19 AS builder

COPY  ./ /work
WORKDIR /work

RUN stack build
RUN cp -r \
    $(stack path --local-install-root)/bin/stack-ghcjs-example.jsexe \
    /sbin/


FROM nginx:1.15.0-alpine

COPY --from=builder \
     /sbin/stack-ghcjs-example.jsexe \
     /usr/share/nginx/html/
