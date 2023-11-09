FROM debian:11


VOLUME ["/data"]

# 修改源
COPY ./sources.list /etc/apt/sources.list

RUN apt update
# 设置时区为"Asia/Shanghai"（您可以根据需要修改时区）
RUN apt install -y tzdata
RUN ln -fs /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata

# 设置默认语言为英语（美国）以及UTF-8字符编码
ENV LANG en_US.UTF-8

# 安装语言环境包和设置默认语言
RUN apt-get install -y locales && \
    sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8

# 工具包
RUN apt install -y --no-install-recommends \
    file curl wget less lsof \
    redis strace supervisor zip vim netcat-traditional \
    dnsutils net-tools inetutils-ping inetutils-traceroute

RUN apt install -y procps iproute2

CMD ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/supervisord.conf"]

