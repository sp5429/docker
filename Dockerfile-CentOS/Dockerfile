FROM sp5429/qgis-server-x64:v4
COPY ./msyh  /usr/share/fonts/
COPY ./ports.conf /etc/apache2/
COPY ./qgis-server.conf /etc/apache2/sites-available/
RUN apt-get update && apt-get install -y binutils \
  && strip --remove-section=.note.ABI-tag /usr/lib/x86_64-linux-gnu/libQt5Core.so.5
CMD apache2-foreground
