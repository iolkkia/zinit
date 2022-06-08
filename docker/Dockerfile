FROM debian:latest

ENV DEBIAN_FRONTEND noninteractive
ENV USER docker

RUN apt-get update \
&& apt-get install -y --no-install-recommends \
  apt-transport-https automake \
  ca-certificates cmake curl \
  file \
  git \
  make \
  subversion sudo \
  unzip \
  wget \
  zsh \
&& rm -rf /var/lib/apt/lists/*

ENV HOME /home/${USER}
RUN useradd \
    --create-home \
    --home-dir ${HOME} ${USER} \
	&& chown -R ${USER}:${USER} ${HOME} \
	&& usermod -a -G sudo,root ${USER} \
  && passwd --delete ${USER}

WORKDIR ${HOME}
USER ${USER}

CMD ["zsh"]
