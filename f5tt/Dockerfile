FROM ubuntu:20.04

ENV TZ=America/Chicago
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
        apt-get install -y -q build-essential python3-pip python3-dev python3-simplejson git nano curl iputils-ping tcpdump bind-utils dnsutils && \
        pip3 install fastapi uvicorn requests clickhouse-driver python-dateutil && \
        # f5ttfs.py
        pip3 install flask && \
        mkdir deployment

WORKDIR /deployment