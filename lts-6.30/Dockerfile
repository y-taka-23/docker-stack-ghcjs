FROM fpco/stack-build:lts-6.30

COPY ./ /work
WORKDIR /work

RUN TAR_OPTIONS=--no-same-owner stack setup --system-ghc
RUN rm -r /work
