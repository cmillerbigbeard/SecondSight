FROM ubuntu:20.04

ENV TZ=America/Chicago
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
        apt-get install -y -q build-essential python3-pip python3-dev python3-simplejson git nano curl iputils-ping tcpdump dnsutils && \
        pip3 install fastapi uvicorn requests clickhouse-driver python-dateutil flask && \
        mkdir deployment
#WORKDIR /deployment

ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/f5ttfs.py /f5ttfs.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/app.py /app.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/nms.py /nms.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/bigiq.py /bigiq.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/cveDB.py /cveDB.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/f5ttCH.py /f5ttCH.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/utils.py /utils.py
ADD https://raw.githubusercontent.com/cmillerbigbeard/SecondSight/main/f5tt/startup.sh /startup.sh

RUN chmod 755 /startup.sh

CMD ./startup.sh