FROM fedora:latest
ARG RUST_VERSION=1.72.1
ENV RUST_VERSION=$RUST_VERSION

RUN dnf install gtk4-devel gcc libadwaita-devel -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN . ~/.cargo/env
RUN ls $HOME/.cargo/env
ENV PATH=/root/.cargo/bin:$PATH
RUN rustup install ${RUST_VERSION}

WORKDIR /mnt

CMD ["/bin/bash"]

