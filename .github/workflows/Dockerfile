FROM alpine:latest
RUN apk update && apk --no-cache add openjdk17
RUN java -version && mkdir -p /var/opt/CrushFTP10_PC
ADD .github/workflows/CrushFTP/CrushFTP10.zip /var/opt/CrushFTP10_PC/
RUN unzip /var/opt/CrushFTP10_PC/CrushFTP10.zip
RUN chown -Rf root:root /var/opt/CrushFTP10_PC
RUN ls -l /var/opt/CrushFTP10_PC
USER root:root
WORKDIR /var/opt/CrushFTP10_PC
CMD java -Xms512m -Xmx4096m -jar /var/opt/CrushFTP10_PC/CrushFTP.jar -dmz 9000
