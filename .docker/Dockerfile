FROM ubuntu:focal

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT [ "/entrypoint.sh" ]

RUN \
    chmod +x /entrypoint.sh &&\
    apt update &&\
    apt install -y jq curl wget libc-bin libatomic1 &&\
    rm -rf /var/lib/apt/lists/*



WORKDIR /altv
COPY server.cfg /altv/server.cfg
COPY update.cfg /altv/update.cfg
ADD https://raw.githubusercontent.com/Lhoerion/altv-serverupdater/master/update.sh /altv/update.sh

RUN \
    chmod +x /altv/update.sh &&\
    bash /altv/update.sh --no-backup --no-logfile &&\
    chmod +x /altv/altv-server

CMD [ "/altv/altv-server" ]
