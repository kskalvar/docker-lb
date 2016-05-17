FROM nginx:latest

RUN apt-get update && apt-get install -y unzip wget

ADD files/start.sh /bin/start.sh
RUN chmod +x /bin/start.sh
ADD files/default.ctmpl /templates/default.ctmpl

RUN wget https://releases.hashicorp.com/consul-template/0.12.2/consul-template_0.12.2_linux_amd64.zip
RUN unzip consul-template_0.12.2_linux_amd64.zip -d /usr/local/bin

# Remove all other conf files from nginx
RUN rm /etc/nginx/conf.d/*

EXPOSE 80
ENTRYPOINT ["/bin/start.sh"]
