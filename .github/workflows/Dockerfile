FROM alpine:latest
RUN apk update && apk --no-cache add openjdk17
RUN java -version && mkdir -p /var/opt/CrushFTP10_PC
RUN unzip .github/workflows/CrushFTP/CrushFTP10.zip -d .github/workflows/build/
COPY .github/workflows/build/ /var/opt/CrushFTP10_PC
RUN chown -Rf root:root /var/opt/CrushFTP10_PC
RUN ls -l /var/opt/CrushFTP10_PC
USER root:root
WORKDIR /var/opt/CrushFTP10_PC
CMD java -Xms512m -Xmx4096m -jar /var/opt/CrushFTP10_PC/CrushFTP.jar -dmz 9000
