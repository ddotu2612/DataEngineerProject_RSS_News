# FROM confluentinc/cp-kafka:5.3.5
FROM confluentinc/cp-kafka:7.4.0

# Chuyển sang người dùng root
USER root

ENV KAFKA_CONFLUENT_SUPPORT_METRICS_ENABLE "false"
ENV KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR "1"
ENV KAFKA_HEAP_OPTS "-Xmx512m -Xms512m"

ADD create_default_topic.sh .

# RUN  apt-get update \
# && apt-get install --force-yes -y net-tools \
# && chmod +x ./create_default_topic.sh

# Cài đặt net-tools bằng yum
RUN yum clean all && yum update -y --skip-broken && yum install -y net-tools

# Cấp quyền thực thi cho script
RUN chmod +x ./create_default_topic.sh

CMD [ "./create_default_topic.sh" ]
