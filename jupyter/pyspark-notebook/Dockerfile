FROM jupyter/pyspark-notebook:3772fffc4aa4
# docker build . -t pyspark-notebook_3772fffc4aa4

MAINTAINER Allen tGuo(yxakuo@hotmail.com)

USER root

# localize
RUN apt update && \
    apt install -yq --no-install-recommends \
      apt-utils

RUN apt install -yq --no-install-recommends \
      tzdata gcc && \
    apt clean && \
    rm -rf /var/lib/apt/lists/*

ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    echo $TZ > /etc/timezone && \
    dpkg-reconfigure -f noninteractive tzdata

USER $NB_USER

RUN pip install --upgrade pip
RUN pip install lxml
RUN pip install tushare psycopg2-binary raven raven redis kombu jupyterlab ta-lib
