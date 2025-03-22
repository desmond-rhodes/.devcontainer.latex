FROM debian:bookworm

RUN \
	apt-get update && \
	apt-get -y dist-upgrade && \
	apt-get -y autopurge && \
	apt-get -y install \
		latexmk \
		locales \
		texlive-bibtex-extra \
		texlive-xetex \
	&& \
	sed -i '/en_US.UTF-8/s/^# //g' /etc/locale.gen && \
	locale-gen && \
	useradd devcontainer --shell /bin/bash --create-home

ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US:en
ENV LC_ALL=en_US.UTF-8

USER devcontainer
WORKDIR /home/devcontainer

USER root
RUN apt-get -y install \
	man \
	less \
	vim \
	git
USER devcontainer
