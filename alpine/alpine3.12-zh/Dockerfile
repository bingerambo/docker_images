FROM digiboy2008/alpine3.12-glibc:v1

ENV LANG C.UTF-8

# 设置时区

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN apk add --no-cache tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    #&& ln -sf /etc/localtime /usr/share/zoneinfo/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    #&& RUN dpkg-reconfigure --frontend noninteractive tzdata \
    && rm -rf /var/cache/apk/* /tmp/* /var/tmp/* $HOME/.cache ## 清除缓存

ENV TZ Asia/Shanghai


# docker build -t alpine:3.12-zh . --network=host