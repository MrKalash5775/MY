FROM debian

FROM debian

COPY debian.list /Users/mrkalash/Documents/GitHub/docker_Lab_1/

RUN 	apt-get update && \
        apt-get install -y procps && \
	apt-get -y upgrade && \
	apt-get -y install nginx && \
	apt-get clean && \
	rm -rf /var/www/* && \
	mkdir -p /var/www/company.com/img
	
COPY index.html /var/www/company.com/
COPY img3.jpg /var/www/company.com/img
RUN	chmod -R 754 var/www/company.com && \
	 useradd slava && \
    groupadd kalashnikov  && \
    usermod -aG kalashnikov slava && \
    chown -R slava:kalashnikov /var/www/company.com && \
    sed -i 's/\/var\/www\/html/\/var\/www\/company.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user slava/g' /etc/nginx/nginx.conf
CMD ["nginx", "-g", "daemon off;"]
