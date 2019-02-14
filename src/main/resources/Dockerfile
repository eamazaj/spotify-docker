FROM debian:stretch-slim

ENV USER user
LABEL maintainer = Edwin Maza Jara <eamazaj@gmail.com>

COPY shell/hello.sh /tmp/
RUN groupadd -r $USER && useradd -r -g $USER -m -d /home/$USER $USER \
&& mv /tmp/hello.sh /opt \
&& chown -Rf $USER:$USER /opt \
&& chmod +x /opt/*.sh \
&& echo 'export PS1="🐳  \[\033[1;36m\]\h \[\033[1;34m\]\w\[\033[0;35m\] \[\033[1;36m\]# \[\033[0m\]"' >> /home/$USER/.bashrc && \
      echo 'export LS_OPTIONS="--color=auto"' >> /home/$USER/.bashrc  && \
      echo 'alias ls="ls $LS_OPTIONS"' >> /home/$USER/.bashrc  && \
      echo 'alias ll="ls $LS_OPTIONS -l"' >> /home/$USER/.bashrc  && \
      echo 'alias l="ls $LS_OPTIONS -lA"' >> /home/$USER/.bashr
USER $USER
WORKDIR /opt
ENTRYPOINT sh /opt/hello.sh