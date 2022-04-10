FROM almalinux:8.5

LABEL maintainer="Song Qian<333355@qq.com>"

ENV JAVA_HOME=/usr/lib/jvm/adoptopenjdk-8-openj9xl
ENV CLASSPATH=.:$JAVA_HOME/lib/tools.jar:/lib.dt.jar
ENV PATH=$JAVA_HOME/bin:$JAVA_HOME/jre/bin:/usr/share/maven/bin:$PATH

WORKDIR /root

#安装jdk8和maven3.5.4
RUN mkdir /opt/tool -p && yum install wget -y && \
	cd /opt/tool && \
	wget "https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK/rpm/centos8-x86_64/Packages/adoptopenjdk-8-openj9xl-8u282-b08.openj9-0.24.0-3.x86_64.rpm" && \
	yum localinstall adoptopenjdk-8-openj9xl-8u282-b08.openj9-0.24.0-3.x86_64.rpm -y && \
	rm -rf adoptopenjdk-8-openj9xl-8u282-b08.openj9-0.24.0-3.x86_64.rpm && \
	wget "https://mirrors.tuna.tsinghua.edu.cn/apache/maven/maven-3/3.5.4/binaries/apache-maven-3.5.4-bin.tar.gz" && \
	tar xf apache-maven-3.5.4-bin.tar.gz && \
	rm -rf apache-maven-3.5.4-bin.tar.gz && \
	ln -s /opt/tool/apache-maven-3.5.4 /usr/share/maven && \
	yum clean all 

CMD ["tail","-f","/etc/hosts"]
