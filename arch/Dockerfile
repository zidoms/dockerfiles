FROM archlinux/base
MAINTAINER Mohammad Zolfaghari <zidom72@gmail.com>

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN pacman -Sy
RUN pacman -S --noconfirm base-devel git hub fish

ARG user=zoli
RUN useradd -m $user
RUN echo "$user ALL=(ALL:ALL) NOPASSWD:ALL" >> /etc/sudoers
USER $user
WORKDIR /home/$user

RUN git clone https://aur.archlinux.org/yay.git && \
	cd yay && \
	sudo -u zoli makepkg -sri --needed --noconfirm && \
	cd && rm -rf .cache yay

RUN yay -S fd fzf --noconfirm neovim icons-in-terminal

RUN git clone https://github.com/zoli/dotfiles.git ~/.dotfiles
RUN ln -s ~/.dotfiles/tmux.conf ~/.tmux.conf
RUN ln -s ~/.dotfiles/gitignore ~/.gitignore
RUN ln -s ~/.dotfiles/gitconfig ~/.gitconfig
RUN ln -s ~/.dotfiles/nvim ~/.config/nvim
RUN ln -s ~/.dotfiles/fish ~/.config/fish
