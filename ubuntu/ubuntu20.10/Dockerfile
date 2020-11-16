FROM ubuntu:20.10

RUN apt-get update && \
       apt-get install -y language-pack-zh-hant language-pack-zh-hans

ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get install tzdata
RUN dpkg-reconfigure --frontend noninteractive tzdata
RUN locale-gen zh_CN.UTF-8 && \
  DEBIAN_FRONTEND=noninteractive dpkg-reconfigure locales
RUN locale-gen zh_CN.UTF-8
ENV LANG zh_CN.UTF-8
ENV LANGUAGE zh_CN:zh
ENV LC_ALL zh_CN.UTF-8

# docker build -t ubuntu:20.10-zh .