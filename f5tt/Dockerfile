FROM ubuntu:20.04

ENV TZ=America/Chicago
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
        apt-get install -y -q build-essential python3-pip python3-dev python3-simplejson git nano curl iputils-ping tcpdump dnsutils && \
        pip3 install fastapi uvicorn requests clickhouse-driver python-dateutil flask && \
        mkdir deployment

WORKDIR /deployment

COPY f5ttfs.py /deployment/
COPY app.py /deployment/
COPY nms.py /deployment/
COPY bigiq.py /deployment/
COPY cveDB.py /deployment/
COPY f5ttCH.py /deployment/
COPY utils.py /deployment/
COPY startup.sh /deployment/

RUN chmod +x startup.sh

CMD ./deployment/startup.sh