# docker build -t professorgrumps/x-burp
# docker run -dti -p 8080:8080 --name x-burp -e DISPLAY=192.168.99.1:0 -v /tmp/.X11-unix:/tmp/.X11-unix professorgrumps/x-burp
# proxy will 192.168.99.100:8080 for docker-machine

FROM openjdk:8u121-jre-alpine
LABEL maintainer "professorgrumps <professorgrumps@gmail.com>"

ENV BURP_VERSION 1.7.32

RUN apk --update add openssl ca-certificates ttf-dejavu curl && \
   rm -f /var/cache/apk/* && \
   mkdir -p /opt/burp /work && \
   adduser -D -s /bin/sh user user && \
   chown -R user /work && \
   curl -sSL -o /opt/burp/burp.jar "https://portswigger.net/burp/releases/download?product=community&version=${BURP_VERSION}&type=jar" && \
   chown -R user /home/user/.*

USER user
WORKDIR /work
EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/opt/burp/burp.jar"]
