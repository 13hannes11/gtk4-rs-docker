FROM fedora:latest
ENV RUST_VERSION=1.60.0

RUN dnf install gtk4-devel gcc libadwaita-devel -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN . ~/.cargo/env
RUN ls $HOME/.cargo/env
ENV PATH=/root/.cargo/bin:$PATH
RUN rustup install ${RUST_VERSION}

WORKDIR /mnt

CMD ["/bin/bash"]

