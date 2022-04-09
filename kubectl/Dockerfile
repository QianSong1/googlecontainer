FROM almalinux:8.5

LABEL maintainer="Song Qian<333355@qq.com>"

WORKDIR /root

RUN mkdir /opt/tool -p && yum install wget -y &&
	cd /opt/tool &&
	wget https://storage.googleapis.com/kubernetes-release/release/v1.21.10/kubernetes-server-linux-amd64.tar.gz &&
	tar xf kubernetes-server-linux-amd64.tar.gz &&
	rm kubernetes-server-linux-amd64.tar.gz -rf &&
	\cp kubernetes/server/bin/kubectl /usr/local/bin/ &&
	kubectl version &&
	yum clean all &&
 	rm -rf ./*

CMD ["tail","-f","/etc/hosts"]
