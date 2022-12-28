FROM ubuntu:22.04       
ENV TZ=Europe/Stockholm
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ARG scikit_learn_version="1.2.0"

ARG build_date
ARG spark_version="3.3.1"
#inconsistency in the repository of spark-hadoop .. use hadoop versoin 3.2 when getting spark 3.2.3 but for newer use only hadoop version 3
ARG hadoop_version="3" 
ARG scala_version="2.12.10"
ARG build_date
ARG shared_workspace=/opt/workspace

RUN apt update && apt upgrade &&  apt-get -y install curl r-base openjdk-8-jre-headless
RUN apt install -y software-properties-common && add-apt-repository universe && apt update && apt install -y \
  python3.10 \
  python3-pip \
  python3-dev \
  && pip3 install --upgrade pip \
  && rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/python3.10 /usr/bin/python
RUN mkdir -p ${shared_workspace}/data
RUN mkdir -p /usr/share/man/man1
RUN curl https://downloads.lightbend.com/scala/2.12.10/scala-${scala_version}.deb -k -o scala.deb
RUN apt install -y ./scala.deb
RUN rm -rf scala.deb /var/lib/apt/lists/*

RUN pip3 install joblib
RUN pip3 install joblibspark
RUN pip3 install scikit-learn==${scikit_learn_version}
RUN pip3 install scikit-spark

ENV SCALA_HOME="/usr/bin/scala"
ENV PATH=${PATH}:${SCALA_HOME}/bin
ENV SHARED_WORKSPACE=${shared_workspace}

VOLUME ${shared_workspace}
CMD ["bash"]

RUN curl https://archive.apache.org/dist/spark/spark-${spark_version}/spark-${spark_version}-bin-hadoop${hadoop_version}.tgz -o spark.tgz && \
    tar -xf spark.tgz && \
    mv spark-${spark_version}-bin-hadoop${hadoop_version} /usr/bin/ && \
    echo "alias pyspark=/usr/bin/spark-${spark_version}-bin-hadoop${hadoop_version}/bin/pyspark" >> ~/.bashrc && \
    echo "alias spark-shell=/usr/bin/spark-${spark_version}-bin-hadoop${hadoop_version}/bin/spark-shell" >> ~/.bashrc && \
    mkdir /usr/bin/spark-${spark_version}-bin-hadoop${hadoop_version}/logs && \
    rm spark.tgz

ENV SPARK_HOME /usr/bin/spark-${spark_version}-bin-hadoop${hadoop_version}
ENV SPARK_MASTER_HOST spark-master
ENV SPARK_MASTER_PORT 7077
RUN cp -fr /usr/bin/python3.10 /usr/bin/python3.9
ENV PYSPARK_PYTHON=/usr/bin/python3.10
ENV PYSPARK_DRIVER_PYTHON=/usr/bin/python3.10
