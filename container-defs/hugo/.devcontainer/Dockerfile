# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.148.1/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version: buster, stretch
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}
USER vscode
ENV HTTP_PROXY=${HTTP_PROXY}
ENV HTTPS_PROXY=${HTTPS_PROXY}
ARG GOVERSION="1.15.4"
ARG GOPKGNAME="go${GOVERSION}.linux-amd64.tar.gz"
ARG GOPKGURL="https://golang.org/dl/${GOPKGNAME}"

# ** [Optional] Uncomment this section to install additional packages. **
RUN sudo apt-get update && export DEBIAN_FRONTEND=noninteractive 
RUN sudo curl --proxy ${HTTP_PROXY} -L "$GOPKGURL" -o "$GOPKGNAME" && sudo tar -C /usr/local -xzf "$GOPKGNAME"
# RUN apt-get -y install --no-install-recommends <your-package-list-here>
ENV PATH="$PATH:/usr/local/go/bin"

RUN cd $HOME && git clone https://github.com/gohugoio/hugo.git
RUN sudo apt-get install -y build-essential
RUN cd $HOME/hugo && go install --tags extended

ENV PATH=$PATH:/home/vscode/go/bin

