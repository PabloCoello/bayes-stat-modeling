FROM ubuntu:20.04
ARG SSH_KEY
ARG SSH_PRV_KEY
ARG DEBIAN_FRONTEND=noninteractive

# Install base dependencies
RUN apt-get update && apt-get install -y \
    git \
    openssh-client \ 
    wget \
    curl \
    cmake \
    unzip \
    software-properties-common \
    libssl-dev \
    libxml2-dev \
    libcurl4-openssl-dev \
    libv8-dev \
    build-essential \
    gdebi-core \
    locales \
    pandoc \
    pandoc-citeproc \
    libv8-dev \
    python3 \
    python3-pip \
    && rm -rf /var/lib/apt/lists/*

RUN add-apt-repository ppa:marutter/rrutter4.0
RUN add-apt-repository ppa:c2d4u.team/c2d4u4.0+
RUN apt update

RUN python3 -m pip install --upgrade pip

RUN locale-gen en_US.UTF-8
RUN update-locale LANG=en_US.UTF-8

ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

## Install R
RUN wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | tee -a /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc
RUN add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu $(lsb_release -cs)-cran40/"
RUN apt-get update && apt install -y --no-install-recommends r-base

## Install Quarto
RUN curl -LO https://quarto.org/download/latest/quarto-linux-amd64.deb
RUN gdebi --non-interactive quarto-linux-amd64.deb

## Install Tinytex
RUN quarto install tinytex

# Remove SSH keys
RUN rm -rf /root/.ssh/

# Python dependencies
COPY requirements/requirements.txt .
RUN python3 -m pip install -r requirements.txt

# R dependencies
COPY ./requirements/requirements-bin.txt .
RUN cat requirements-bin.txt | xargs apt-get install -y -qq
COPY ./requirements/requirements-src.R .
RUN Rscript requirements-src.R

# Clone base repo
# Authorize SSH Host
RUN mkdir -p /root/.ssh && \
    chmod 0700 /root/.ssh && \
    ssh-keyscan github.com > /root/.ssh/known_hosts

# Add the keys and set permissions
RUN echo "$SSH_PRV_KEY" > /root/.ssh/id_rsa && \
    echo "$SSH_KEY" > /root/.ssh/id_rsa.pub && \
    chmod 600 /root/.ssh/id_rsa && \
    chmod 600 /root/.ssh/id_rsa.pub

# Clean up package registry
RUN rm -rf /var/lib/apt/lists/*

# copying all files over
WORKDIR /src/bayes-stat-modeling/
ADD . /src/bayes-stat-modeling/