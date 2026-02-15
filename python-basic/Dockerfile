FROM	ubuntu
RUN	apt update
RUN	apt install python3 python3-pip -y
RUN 	apt install python3-flask -y
WORKDIR /app
EXPOSE	5000
COPY	app.py .
CMD 	["python3", "app.py"]

