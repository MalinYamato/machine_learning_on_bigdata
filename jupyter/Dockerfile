FROM ubuntu:22.04       
ENV TZ=Europe/Stockholm
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ARG build_date
ARG spark_version="3.3.0"
ARG jupyterlab_version="3.5.0"
ARG scala_kernel_version="0.10.9"
ARG scala_version="2.12.10"
ARG scikit_learn_version="1.2.0"
ARG scikit-spark_version"0.4.0"

ARG shared_workspace=/opt/workspace
RUN mkdir -p ${shared_workspace}/data
RUN mkdir -p /usr/share/man/man1
RUN ln -sf /usr/bin/python3.9 /usr/bin/python3

RUN apt update && apt upgrade &&  apt-get -y install curl r-base openjdk-8-jre-headless
RUN apt install -y software-properties-common && add-apt-repository universe && apt update && apt install -y \
  python3.10 \
  python3-pip \
  python3-dev \
  && pip3 install --upgrade pip \ 
  && rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/python3.10 /usr/bin/python
RUN curl https://downloads.lightbend.com/scala/2.12.10/scala-${scala_version}.deb -k -o scala.deb
RUN apt install -y ./scala.deb
RUN rm -rf scala.deb /var/lib/apt/lists/*

ENV SCALA_HOME="/usr/bin/scala"
ENV PATH=${PATH}:${SCALA_HOME}/bin
ENV SHARED_WORKSPACE=${shared_workspace}

VOLUME ${shared_workspace}
CMD ["bash"]

#JupyterLab + Python kernel for PySpark
COPY workspace/ /workspace/

RUN pip3 install wget pyspark==${spark_version} jupyterlab==${jupyterlab_version}
RUN pip3 install pandas
RUN pip3 install numpy 
RUN pip3 install scipy
RUN pip3 install scikit-learn==${scikit_learn_version}
RUN pip3 install scikit-spark
RUN pip3 install -U matplotlib
RUN pip3 install -U joblibspark
RUN pip3 list

#Scala kernel for Spark
RUN apt-get install -y ca-certificates-java --no-install-recommends
RUN curl -Lo coursier https://git.io/coursier-cli
RUN chmod +x coursier
RUN ./coursier launch --fork almond:${scala_kernel_version} --scala ${scala_version} -- --display-name "Scala ${scala_version}" --install
RUN rm -f coursier

#R kernel for SparkR
RUN apt-get install -y r-base-dev
RUN R -e "install.packages('IRkernel')"
RUN R -e "IRkernel::installspec(displayname = 'R 3.5', user = FALSE)"
RUN curl https://archive.apache.org/dist/spark/spark-${spark_version}/SparkR_${spark_version}.tar.gz -k -o sparkr.tar.gz
RUN R CMD INSTALL sparkr.tar.gz
RUN rm -f sparkr.tar.gz
