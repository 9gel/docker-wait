FROM 9gel/docker-wait

RUN apk add --update mysql-client && rm -rf /var/cache/apk/*
ADD dbadmin /dbadmin
ENTRYPOINT ["/dbadmin"]
