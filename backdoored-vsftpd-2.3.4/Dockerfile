FROM ubuntu:18.04

COPY . /root/
WORKDIR /root/

RUN mkdir /usr/share/empty/ && \
	mkdir /var/ftp/ && \
	useradd -d /var/ftp ftp

RUN chown root.root /var/ftp && \
	chmod og-w /var/ftp

RUN mv vsftpd /usr/local/sbin/vsftpd && \
	mv vsftpd.conf /etc/

RUN echo 'echo Started FTP Server@ `hostname -i 2>/dev/null`:21' > /root/run.sh && \
	echo "/usr/local/sbin/vsftpd" >> /root/run.sh

CMD ["/bin/bash", "-c", "/bin/bash run.sh"]