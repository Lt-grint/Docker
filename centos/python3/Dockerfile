# 基于centos7构建Python3环境
FROM centos:7

MAINTAINER litao <litao_worker@163.com>

RUN yum update -y \
    # 安装python3 
    && yum install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel sqlite-devel \ 
    && yum install -y python3 python3-dev python-pip \

