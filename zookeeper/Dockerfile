FROM kafka_base:1.0.0
MAINTAINER ash@the-rebellion.net

RUN mkdir /opt ; cd /tmp && \
wget -c http://apache.uberglobalmirror.com/zookeeper/zookeeper-3.4.6/zookeeper-3.4.6.tar.gz && \
tar xzf zookeeper-3.4.6.tar.gz && mv zookeeper-3.4.6 /opt
RUN cd /opt/zookeeper-3.4.6 && cp conf/zoo_sample.cfg conf/zoo.cfg
RUN ln -s /opt/zookeeper-3.4.6 /opt/zookeeper

WORKDIR /etc/supervisor.d/

ADD ./config/supervisor.d/* ./

EXPOSE 2181

CMD [ "/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf" ]
