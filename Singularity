Bootstrap: docker
From: ubuntu:16.04

%environment
SHELL=/bin/bash
PATH=/opt/anaconda/bin:${PATH}
LC_ALL=C.UTF-8

%runscript
    echo "This is what happens when you run the container..."
    export PATH=/opt/anaconda/bin:${PATH}

%post
    echo "Hello from inside the container"
    apt-get update
    apt-get -y install wget git bzip2 build-essential gcc zlib1g-dev language-pack-en-base apt-transport-https
    update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8

    cd /root/ && wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
    cd /root/ && chmod 700 ./Miniconda3-latest-Linux-x86_64.sh
    cd /root/ && bash ./Miniconda3-latest-Linux-x86_64.sh -b -p /opt/anaconda/

    export PATH=/opt/anaconda/bin:${PATH}

    pip install https://github.com/moonso/loqusdb/archive/2.1.zip
    
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-3.6.list

    apt-get update
    apt-get install -y mongodb-org

    mkdir -p /data/db

