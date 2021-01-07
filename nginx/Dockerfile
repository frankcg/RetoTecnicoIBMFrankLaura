# instalando nginx
FROM nginx:stable-alpine

#copiando el archivo default a la configuracion del proxy
COPY default.conf /etc/nginx/conf.d

# exponiendo puertos
EXPOSE 80/tcp
EXPOSE 443/tcp

# ejecutando
CMD ["/bin/sh", "-c", "exec nginx -g 'daemon off;';"]

WORKDIR /usr/share/nginx/html