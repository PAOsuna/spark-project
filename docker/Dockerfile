FROM eclipse-temurin:11-jre-jammy

ENV SPARK_HOME=/opt/spark
ENV SPARK_VERSION=3.4.3 \
    HADOOP_VERSION=3 \
    PATH=${PATH}:${SPARK_HOME}/bin:${SPARK_HOME}/sbin

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl bash tini procps \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get clean

RUN set -x \
    && curl -fL "https://archive.apache.org/dist/spark/spark-${SPARK_VERSION}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz" -o spark.tgz \
    && tar -xvzf spark.tgz -C /opt \
    && mv "/opt/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}" "${SPARK_HOME}" \
    && rm spark.tgz \
    && mkdir -p /tmp/spark-events /opt/spark/logs

WORKDIR /workspace
EXPOSE 7077 8080 4040
ENTRYPOINT ["/usr/bin/tini", "--"]
CMD ["/opt/spark/bin/spark-shell", "--master", "local[*]"]