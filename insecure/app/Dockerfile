FROM nextcloud:stable

COPY transifexconf/* /root/

COPY transifexconf/.tx /usr/src/nextcloud/.tx

RUN	\
	apt-get update; \
	apt-get install -y gettext transifex-client;

WORKDIR /usr/src/nextcloud

RUN 	\
	tx pull -l vi; \
	php translationtool.phar convert-po-files;


COPY *.sh upgrade.exclude /

COPY theme /usr/src/nextcloud/vworkspace_theme
