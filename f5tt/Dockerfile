FROM ubuntu:20.04

ENV TZ=Europe/Rome
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
        apt-get install -y -q build-essential python3-pip python3-dev python3-simplejson git nano curl iputils-ping tcpdump bind-utils dnsutils && \
        pip3 install fastapi uvicorn requests clickhouse-driver python-dateutil  && \
        # f5ttfs.py
        pip3 install flask && \
        mkdir deployment

WORKDIR /deployment

COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/f5ttfs.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/app.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/nms.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/bigiq.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/cveDB.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/f5ttCH.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/utils.py .
COPY https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/startup.sh .

RUN chmod +x startup.sh

CMD ./startup.sh
