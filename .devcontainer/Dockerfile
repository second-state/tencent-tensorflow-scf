FROM ubuntu:20.04
ARG DEBIAN_FRONTEND=noninteractive
ENV RUSTUP_HOME=/usr/local/rustup \
    CARGO_HOME=/usr/local/cargo \
    PATH=/usr/local/cargo/bin:$PATH
RUN apt-get update \
    && apt-get install -y tzdata \
    && apt-get -y upgrade && apt-get install -y build-essential curl wget git vim libboost-all-dev llvm-dev liblld-10-dev
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y \
    && /usr/local/cargo/bin/rustup override set 1.50.0
RUN curl -sL https://deb.nodesource.com/setup_12.x |  bash \
    && apt-get install -y nodejs \
    && npm install -y -g rustwasmc --unsafe-perm \
    && npm install -g serverless

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog
