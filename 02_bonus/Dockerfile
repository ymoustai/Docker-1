FROM ubuntu
RUN apt update && DEBIAN_FRONTEND=noninteractive apt install -y tzdata && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN apt-get update \
	&& apt-get install apache2 -y \
		&& apt-get install mysql-server -y \
			&& apt install php libapache2-mod-php php-mysql -y \
				&& apt-get install php-cli -y 
				EXPOSE 443
				EXPOSE 80
				COPY apache2.conf /etc/apache2/apache2.conf
				ENTRYPOINT service apache2 restart && bash
