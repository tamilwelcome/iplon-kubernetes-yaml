FROM ubuntu:20.04

COPY timezone /etc/
COPY localtime /etc/

RUN apt update
RUN apt -y install software-properties-common
RUN apt -y install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev libbz2-dev python python3 python3-pip
RUN pip3 install influxdb_client
## The directory creation are dummy purpose only including the permissions change, everything is handled at the time of deployment
RUN mkdir -p /iporting/microgridlakeasia/tmp/ \
    mkdir -p /iporting/microgridlakeasia/bad/ \
    mkdir -p /iporting/microgridlakeasia/good/ \
    mkdir -p /iporting/smallutilitylakeasia/tmp/ \
    mkdir -p /iporting/smallutilitylakeasia/bad/ \
    mkdir -p /iporting/smallutilitylakeasia/good/ \
    mkdir -p /iporting/largeutilitylakeasia/tmp/ \
    mkdir -p /iporting/largeutilitylakeasia/bad/ \
    mkdir -p /iporting/largeutilitylakeasia/good/ \
    mkdir -p /iporting/ampluslakeasia/tmp/ \
    mkdir -p /iporting/ampluslakeasia/bad/ \
    mkdir -p /iporting/ampluslakeasia/good/ \
    mkdir -p /iporting/iplonlakeasia/tmp/ \
    mkdir -p /iporting/iplonlakeasia/bad/ \
    mkdir -p /iporting/iplonlakeasia/good/ \
    mkdir -p /iporting/microgridlakeafrica/tmp/ \
    mkdir -p /iporting/microgridlakeafrica/bad/ \
    mkdir -p /iporting/microgridlakeafrica/good/ \
    mkdir -p /iporting/microgridlakeamerica/tmp/ \
    mkdir -p /iporting/microgridlakeamerica/bad/ \
    mkdir -p /iporting/microgridlakeamerica/good/ \
    mkdir -p /data/csv-to-smallutilitylakeasia/

COPY ddtcfg /etc/ddtcfg
COPY iporting /usr/bin/iporting
COPY influx /usr/bin/influx
RUN chmod 777 -R /etc/ddtcfg
RUN chmod 777 /usr/bin/iporting \
    & chmod 777 /usr/bin/influx
CMD /usr/bin/iporting
