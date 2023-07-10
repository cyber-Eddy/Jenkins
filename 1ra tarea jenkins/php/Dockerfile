
# FROM jenkins/jenkins:lts
# USER root

# RUN apt-get update && \
#     apt-get install -y apt-transport-https \
#                        ca-certificates \
#                        curl \
#                        gnupg2 \
#                        software-properties-common && \
#     curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
#     add-apt-repository \
#        "deb [arch=amd64] https://download.docker.com/linux/debian \
#        $(lsb_release -cs) \
#        stable" && \
#     apt-get update && \
#     apt-get install -y docker-ce docker-ce-cli containerd.io && \
#     curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
#     chmod +x /usr/local/bin/docker-compose 

# USER jenkins



FROM jenkins/jenkins:lts

RUN apt-get update

# Install Jenkins
RUN apt-get update && apt-get install -y gnupg2 ca-certificates wget

# Descargar e importar la clave GPG de Jenkins
RUN wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | apt-key add -

# Agregar el repositorio de Jenkins al sources.list
RUN sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

RUN apt-get update && apt-get install -y jenkins

# Expose Jenkins port
EXPOSE 8080
