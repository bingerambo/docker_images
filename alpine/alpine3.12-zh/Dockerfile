FROM alpine:3.12

ENV LANG C.UTF-8

RUN apk add --no-cache bash && \
	wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
	wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.32-r0/glibc-2.32-r0.apk && \
	apk add --no-cache glibc-2.32-r0.apk && \
	rm -rf glibc-2.32-r0.apk

# 设置时区
ENV TZ=Asia/Shanghai
# RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN apk add --no-cache tzdata \
    && ln -sf /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone \
    && RUN dpkg-reconfigure --frontend noninteractive tzdata \
    && rm -rf /var/cache/apk/* /tmp/* /var/tmp/* $HOME/.cache ## 清除缓存


# docker build -t alpine:3.12-zh .