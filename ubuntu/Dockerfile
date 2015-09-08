FROM ubuntu:14.04
MAINTAINER Mohammad Zolfaghari <zidom72@gmail.com>

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN apt-get update
RUN apt-get install -y vim curl wget software-properties-common git zsh

RUN git clone --recursive https://github.com/zoli/dotfiles.git ~/.dotfiles
RUN ln -s ~/.dotfiles/vimrc ~/.vimrc
RUN ln -s ~/.dotfiles/vim ~/.vim
RUN ln -s ~/.dotfiles/gitignore ~/.gitignore
RUN ln -s ~/.dotfiles/gitconfig ~/.gitconfig

ADD zshrc /root/.zshrc
