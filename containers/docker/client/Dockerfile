FROM eqitii/eqitii-kademlia:0.1.8

RUN apk add openssl
RUN apk add sed

COPY client /app
WORKDIR /app

COPY containers/docker/client/config/ /app/client-conf/
RUN find /app/client-conf -type f -exec chmod 777 {} \;
RUN pip install -r requirements.txt

ENTRYPOINT ["sh", "/app/client-conf/docker-entry.sh"]
