FROM	ubuntu
RUN 	apt  update
RUN	apt install  nginx -y 
COPY	templatemo_604_christmas_piano/ /var/www/html/
CMD	["nginx", "-g", "daemon off;"]
