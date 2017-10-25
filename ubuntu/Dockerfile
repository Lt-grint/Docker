# 从ubuntu16.04版本构件
FROM ubuntu:16.04

# 作者： litao
MAINTAINER litao <litao_worker@163.com>

# 从apt构建Python3环境
RUN apt update \
    && apt install -y python3 \
    && apt install -y python3-pip \
    && rm -rf /var/lib/apt/lists/* \

RUN mkdir -p /app
WORKDIR /app

EXPOSE 80    
CMD ['bash']
    