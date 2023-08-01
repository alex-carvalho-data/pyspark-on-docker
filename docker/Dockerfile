FROM ubuntu:20.04
LABEL foo.oak.docker.image.authors="alex carvalho" \
      foo.oak.docker.image.name="oak/pyspark" \
      foo.oak.docker.image.version="0.3.4" \
      foo.oak.docker.image.description="Image to mimic Databricks runtime 11.3 LTS" \
      foo.oak.docker.image.java="openjdk-8-jdk"

RUN apt-get update \
    && apt-get upgrade -y \
    && echo "Europe/Zurich" > /etc/timezone \
    && apt-get install -y  \
      openjdk-8-jdk