# Archivo: Dockerfile.c1
FROM ubuntu:16.10

# Arreglar repositorios (Versión EOL)
RUN sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Actualizar e instalar cliente SSH [cite: 19]
# También instalo iputils-ping y tcpdump para facilitar tu análisis de red
RUN apt-get update && apt-get install -y \
    openssh-client \
    iputils-ping \
    tcpdump \
    && rm -rf /var/lib/apt/lists/*

# Mantener el contenedor activo para que puedas entrar
CMD ["tail", "-f", "/dev/null"]