FROM node:alpine3.10

# actualizando paquetes
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh

# Ruta donde se descargara el repositorio - git
WORKDIR /usr/src/app

# Clonando el Repositorio
RUN git clone https://github.com/frankcg/retobase-nodejs.git

# posicionar el directorio para instalar el package
WORKDIR /usr/src/app/retobase-nodejs

# Instalando
RUN npm install --save
RUN npm install mysql

HEALTHCHECK --interval=12s --timeout=12s --start-period=30s \  
    CMD node healthcheck.js

# Exponiendo Puerto
EXPOSE 4000

# Iniciando el Node
CMD [ "npm", "start" ]
