FROM	 ubuntu
RUN 	 apt  update
RUN	   apt install  nginx -y 
COPY	 templatemo_604_christmas_piano/ /var/www/html/
EXPOSE 8081
CMD	   ["nginx", "-g", "daemon off;"]
