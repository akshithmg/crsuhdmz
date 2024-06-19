FROM alpine:latest
RUN apk update && apk --no-cache add openjdk17
RUN apk --no-cache add tzdata
ENV TZ=Australia/Melbourne
RUN java -version && mkdir -p /var/opt/CrushFTP10
ADD https://www.crushftp.com/early10/CrushFTP10.zip -d /var/opt/
#COPY .github/workflows/CrushFTP/CrushFTP10.zip /var/opt/
RUN unzip /var/opt/CrushFTP10.zip -d /var/opt/
RUN rm -rf /var/opt/CrushFTP10.zip
RUN chown -Rf root:root /var/opt/CrushFTP10
RUN ls -l /var/opt/CrushFTP10
USER root:root
WORKDIR /var/opt/CrushFTP10
CMD java -Xms512m -Xmx4096m -jar /var/opt/CrushFTP10/CrushFTP.jar -dmz 9000
