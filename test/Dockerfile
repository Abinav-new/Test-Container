FROM ubuntu:latest
RUN apt update
RUN apt install openssh-server  docker.io -y
RUN apt install nginx -y
RUN service docker start
RUN service docker status
RUN  docker volume create portainer_data
RUN docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
COPY index.html /var/www/html/index.html
EXPOSE 8080
CMD ["nginx", "-g", daemon off;"]
