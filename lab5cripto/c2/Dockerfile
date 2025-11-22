# Archivo: Dockerfile.c2
FROM ubuntu:18.10

# Arreglar repositorios (Versión EOL)
RUN sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Actualizar e instalar cliente SSH [cite: 19]
RUN apt-get update && apt-get install -y \
    openssh-client \
    iputils-ping \
    tcpdump \
    && rm -rf /var/lib/apt/lists/*

CMD ["tail", "-f", "/dev/null"]