FROM ubuntu:20.04

# variables
ENV USER=dev
ENV USER_ID=1000
ENV PASSWORD=docker
ENV WORKSPACE=/home/$USER/workspace

# install general tools
RUN \
  # sed -i "s@http://.*archive.ubuntu.com@http://mirrors.tuna.tsinghua.edu.cn@g" /etc/apt/sources.list && \
  # sed -i "s@http://.*security.ubuntu.com@http://mirrors.tuna.tsinghua.edu.cn@g" /etc/apt/sources.list && \
  apt-get update && \
  DEBIAN_FRONTEND="noninteractive" apt-get install \
  --no-install-recommends -y \
  apt-utils sudo curl git-core gnupg locales \
  nodejs zsh wget nano npm fonts-powerline tmux vim \
  openssh-client

# set up locale
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

# add a user
RUN useradd -u $USER_ID -ms /bin/zsh $USER && \
  echo "$USER:$PASSWORD" | chpasswd && adduser $USER sudo
USER $USER

# run zsh installation script
RUN git config --global init.defaultBranch main
RUN sh -c "$(curl -fsSL \
  https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

#config zsh


# set workdir
WORKDIR $WORKSPACE

# start zsh
ENTRYPOINT [ "/bin/zsh" ]

