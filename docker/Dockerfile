FROM ubuntu:20.04
LABEL foo.oak.docker.image.authors="alex carvalho" \
      foo.oak.docker.image.name="oak/pyspark" \
      foo.oak.docker.image.version="0.4.11" \
      foo.oak.docker.image.description="Image to mimic Databricks runtime 11.3 LTS" \
      foo.oak.docker.image.java="openjdk-8-jdk" \
      foo.oak.docker.image.python="3.9"

RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y  \
        openjdk-8-jdk

RUN apt-get install -y \
        curl \
        git \
        build-essential \
        libssl-dev \
        zlib1g-dev \
        libbz2-dev \
        libreadline-dev \
        libsqlite3-dev \
        libncursesw5-dev \
        xz-utils \
        tk-dev \
        libxml2-dev \
        libxmlsec1-dev \
        libffi-dev \
        liblzma-dev \
    && curl https://pyenv.run | bash \
    && echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc \
    && echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc \
    && echo 'eval "$(pyenv init -)"' >> ~/.bashrc \
    && echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile \
    && echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile \
    && echo 'eval "$(pyenv init -)"' >> ~/.profile

ARG PYENV_VERSION=3.9.5

ENV HOME="/root"
ENV PYENV_ROOT="${HOME}/.pyenv"
ENV PATH="$PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH"
ENV PYENV_VERSION=${PYENV_VERSION}

RUN pyenv install $PYENV_VERSION

ENV POETRY_HOME="/etc/poetry"
ENV PATH="$POETRY_HOME/bin:$PATH"

RUN curl -sSL https://install.python-poetry.org | python3 -
