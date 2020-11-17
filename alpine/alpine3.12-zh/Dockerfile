FROM alpine3.12-glibc:v1

ENV LANG C.UTF-8

# 设置时区
ENV TZ Asia/Shanghai
# RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN apk add --no-cache tzdata \
    && ln -sf /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone \
    && RUN dpkg-reconfigure --frontend noninteractive tzdata \
    && rm -rf /var/cache/apk/* /tmp/* /var/tmp/* $HOME/.cache ## 清除缓存


# docker build -t alpine:3.12-zh .