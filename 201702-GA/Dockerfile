FROM keensoft/centos7-java8-tomcat7.0.69
MAINTAINER keensoft.es

RUN yum update -y
RUN yum install -y unzip 

ENV ALF_DOWNLOAD_URL https://download.alfresco.com/release/community/201702-build-00016/alfresco-community-distribution-201702.zip
ENV ALF_HOME /usr/local/alfresco

RUN set -x \
	&& mkdir -p $ALF_HOME \
	&& wget --no-check-certificate $ALF_DOWNLOAD_URL \
	&& unzip alfresco-community-distribution-201702.zip -d /tmp \
	&& rm -f alfresco-community-distribution-201702.zip

WORKDIR $ALF_HOME
ENV DIST /tmp/alfresco-community-distribution-201702
ENV PATH $ALF_HOME/bin:$PATH

EXPOSE 8080
CMD ["catalina.sh", "run"]
