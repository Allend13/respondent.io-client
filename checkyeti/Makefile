CY_DB_PASS=yeti
CY_DB_USER=yeti
GRAILS_OPTS="-Xmx2072m -Xms256m -XX:PermSize=128m -XX:MaxPermSize=2096m -Dfile.encoding=UTF-8"
IP=$(shell ifconfig | grep -Eo 'inet (addr:)?([0-9]*\.){3}[0-9]*' | grep -Eo '([0-9]*\.){3}[0-9]*' | grep -v '127.0.0.1' | awk '{print $1}')
AWS_ACCESS_KEY=AKIAI2ZH6IMDDK2GYMMA
AWS_SECRET_KEY=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


start-places:
	export TOMCAT_SERVER=$(IP) CY_DB_PASS=$(CY_DB_PASS) CY_DB_USER=$(CY_DB_USER) AWS_ACCESS_KEY=$(AWS_ACCESS_KEY) AWS_SECRET_KEY=$(AWS_SECRET_KEY); \
	export CY_DB_URL="jdbc:mysql://$(IP):3306/yeti?zeroDateTimeBehavior=convertToNull&autoReconnect=true&useSSL=false" ; \
	cd ./docker/services && docker-compose up place-service; \

start:
	export TOMCAT_SERVER=$(IP) CY_DB_PASS=$(CY_DB_PASS) CY_DB_USER=$(CY_DB_USER) AWS_ACCESS_KEY=$(AWS_ACCESS_KEY) AWS_SECRET_KEY=$(AWS_SECRET_KEY); \
	export CY_DB_URL="jdbc:mysql://$(IP):3306/yeti?zeroDateTimeBehavior=convertToNull&autoReconnect=true&useSSL=false" ; \
	cd ./docker/infra && docker-compose up -d; \
	cd ../services && docker-compose up -d; \
	cd ../../checkyeti && ./run-app.sh

restart-places:
	export TOMCAT_SERVER=$(IP) CY_DB_PASS=$(CY_DB_PASS) CY_DB_USER=$(CY_DB_USER) AWS_ACCESS_KEY=$(AWS_ACCESS_KEY) AWS_SECRET_KEY=$(AWS_SECRET_KEY); \
	export CY_DB_URL="jdbc:mysql://$(IP):3306/yeti?zeroDateTimeBehavior=convertToNull&autoReconnect=true&useSSL=false" ; \
	cd ./docker/services && docker-compose stop place-service && docker-compose up place-service;

stop:
	cd ./docker/infra && docker-compose stop
	cd ./docker/services && docker-compose stop