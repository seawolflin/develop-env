FROM mcr.microsoft.com/devcontainers/base:jammy

ENV USER=vscode


# config zsh
COPY .zshrc /home/${USER}/
RUN \
  git clone https://github.com/zsh-users/zsh-autosuggestions /home/${USER}/.oh-my-zsh/custom/plugins/zsh-autosuggestions \
  && git clone https://github.com/zsh-users/zsh-history-substring-search /home/${USER}/.oh-my-zsh/custom/plugins/zsh-history-substring-search \
  && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git /home/${USER}/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting

# start zsh
ENTRYPOINT [ "/bin/zsh" ]
