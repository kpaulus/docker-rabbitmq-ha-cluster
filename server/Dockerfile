FROM bijukunjummen/rabbitmq-base

ADD rabbitmq.config /etc/rabbitmq/

RUN chmod u+rw /etc/rabbitmq/rabbitmq.config

ADD erlang.cookie /var/lib/rabbitmq/.erlang.cookie

RUN chown rabbitmq:rabbitmq /var/lib/rabbitmq/.erlang.cookie

RUN chmod 400 /var/lib/rabbitmq/.erlang.cookie

RUN mkdir /opt/rabbit

ADD startrabbit.sh /opt/rabbit/

RUN chmod a+x /opt/rabbit/startrabbit.sh

EXPOSE 5672
EXPOSE 1883
EXPOSE 15672

CMD /opt/rabbit/startrabbit.sh
