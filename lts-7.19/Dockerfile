FROM fpco/stack-build:lts-7.19

COPY ./ /work
WORKDIR /work

RUN TAR_OPTIONS=--no-same-owner stack setup --system-ghc
RUN rm -r /work
