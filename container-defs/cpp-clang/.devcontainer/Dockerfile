# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.148.0/containers/cpp/.devcontainer/base.Dockerfile

# [Choice] Debian / Ubuntu version: debian-10, debian-9, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-${VARIANT}

# [Optional] Uncomment this section to install additional packages.
RUN export HTTP_PROXY=${HTTP_PROXY} && HTTPS_PROXY=${HTTP_PROXY} && apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends lsb-release wget software-properties-common
RUN export HTTP_PROXY=${HTTP_PROXY} && HTTPS_PROXY=${HTTP_PROXY} && bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)"