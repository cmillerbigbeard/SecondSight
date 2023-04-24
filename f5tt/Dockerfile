FROM ubuntu:20.04

ENV TZ=America/Chicago
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
        apt-get install -y -q build-essential python3-pip python3-dev python3-simplejson git nano curl iputils-ping tcpdump dnsutils && \
        pip3 install fastapi uvicorn requests clickhouse-driver python-dateutil flask && \
        mkdir deployment
WORKDIR /deployment

ADD ./f5tt/f5ttfs.py /f5ttfs.py
ADD ./f5tt/app.py /app.py
ADD ./f5tt/nms.py /nms.py
ADD ./f5tt/bigiq.py /bigiq.py
ADD ./f5tt/cveDB.py /cveDB.py
ADD ./f5tt/f5ttCH.py f5ttCH.py
ADD ./f5tt/utils.py /utils.py
ADD ./f5tt/startup.sh /startup.sh

RUN chmod +x /startup.sh

CMD ./startup.sh