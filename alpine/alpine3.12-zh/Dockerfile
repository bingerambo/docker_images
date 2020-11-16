FROM alpine:3.12


RUN apk update && \
       apk add language-pack-zh-hant language-pack-zh-hans

ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apk add tzdata
RUN dpkg-reconfigure --frontend noninteractive tzdata
RUN locale-gen zh_CN.UTF-8 && \
  DEBIAN_FRONTEND=noninteractive dpkg-reconfigure locales
RUN locale-gen zh_CN.UTF-8
ENV LANG zh_CN.UTF-8
ENV LANGUAGE zh_CN:zh
ENV LC_ALL zh_CN.UTF-8

# docker build -t alpine:3.12-zh .