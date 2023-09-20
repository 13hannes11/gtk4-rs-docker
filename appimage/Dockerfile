FROM fedora:latest
ARG RUST_VERSION=1.64.0
ENV RUST_VERSION=$RUST_VERSION

RUN dnf install gtk4-devel gcc libadwaita-devel -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN . ~/.cargo/env
RUN ls $HOME/.cargo/env
ENV PATH=/root/.cargo/bin:$PATH
RUN rustup install ${RUST_VERSION}


ENV APPIMAGE_VERSION=13
ENV APPIMAGE_EXTRACT_AND_RUN=1

RUN cargo install cargo-appimage

RUN dnf install wget -y

RUN wget https://github.com/AppImage/AppImageKit/releases/download/$APPIMAGE_VERSION/appimagetool-x86_64.AppImage
RUN chmod +x appimagetool-x86_64.AppImage
RUN ./appimagetool-x86_64.AppImage --appimage-extract
RUN ls
RUN ln -nfs /squashfs-root/usr/bin/appimagetool /usr/bin/appimagetool

RUN dnf install file desktop-file-utils appstream -y

WORKDIR /mnt

CMD ["/bin/bash"]
