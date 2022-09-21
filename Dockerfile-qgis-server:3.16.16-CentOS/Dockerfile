FROM sp5429/qgis-server-x64:v2.1
RUN apt-get update && apt-get install -y binutils \
  && strip --remove-section=.note.ABI-tag /usr/lib/x86_64-linux-gnu/libQt5Core.so.5
CMD apache2-foreground