---
layout: post
title:  Linux Setting
---
민트 리눅스 개발 환경 구축

>>JAVA

- opjdk remove
sudo apt-get purge openjdk-\*

- jdk
unzip /usr/local/jdk1.8.0_65

sudo ln -s jdk1.8.0_65/ java

- tomcat
unzip /usr/local/apache-tomcat-8.0.30

sudo ln -s apache-tomcat-8.0.30/ tomcat8


>>DASOM 입력기

https://github.com/dasom-im/dasom/releases/tag/1.2 : download

sudo add-apt-repository ppa:dasom/ppa
sudo apt update
sudo apt-get install dasom dasom-gtk dasom-qt dasom-jeongeum

im-config

- git install 
sudo apt-get install git

- zsh install 
vim /etc/pam.d/chsh  require 주석 처리 

chsh -s /usr/bin/zsh

- Oh my zsh install
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
.zshrc 편집 ZSH_THEME="ys"

>>python

sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev

- pyenv install : https://github.com/yyuu/pyenv

git clone https://github.com/yyuu/pyenv.git ~/.pyenv 

- pyenv-virtualenv : https://github.com/yyuu/pyenv-virtualenv

git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv

.zshrc add 
export PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/local/java/bin:/usr/local/tomcat8/bin"

export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"


- pyenv install 2.7.10, pyenv install 3.5.0 

pyenv rehash

- pyenv + virtualenv use

pyenv virtualenv PYTHON_VERSION VIRTUAL_ENV_NAME 으로 새로운 개발 환경을 만들 수 있다.

pyenv virtualenv 2.7.10 env-2.7.10
pyenv virtualenv 3.5.0 env-3.5.0

pyenv versions
pyenv install 2.7.10
pyenv shell 2.7.10
