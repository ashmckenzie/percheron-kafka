FROM kafka_base:1.0.0
MAINTAINER ash@the-rebellion.net

RUN mkdir /opt ; cd /tmp && \
wget -c http://apache.mirror.digitalpacific.com.au//kafka/0.8.2.1/kafka_2.11-0.8.2.1.tgz && \
tar xzf kafka_2.11-0.8.2.1.tgz && mv kafka_2.11-0.8.2.1 /opt/kafka-0.8.2.1
RUN ln -s /opt/kafka-0.8.2.1 /opt/kafka

ADD ./config/kafka/server.properties /opt/kafka/config/

WORKDIR /etc/supervisor.d/
ADD ./config/supervisor.d/* ./

EXPOSE 9092

CMD [ "/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf" ]
