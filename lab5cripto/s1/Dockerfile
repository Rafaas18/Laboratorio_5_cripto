# Archivo: Dockerfile.c4
FROM ubuntu:22.10

# Arreglar repositorios (Versión EOL)
RUN sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Actualizar e instalar Cliente y Servidor SSH [cite: 19]
RUN apt-get update && apt-get install -y \
    openssh-client \
    openssh-server \
    iputils-ping \
    tcpdump \
    && rm -rf /var/lib/apt/lists/*



# Crear usuario 'prueba' con contraseña 'prueba' [cite: 20]
RUN useradd -m -s /bin/bash prueba && \
    echo 'prueba:prueba' | chpasswd

# Permitir autenticación por contraseña (a veces viene deshabilitada por defecto en nuevas versiones)
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config

# Exponer el puerto 22
EXPOSE 22

# Iniciar el servicio SSH
CMD ["/usr/sbin/sshd", "-D"]