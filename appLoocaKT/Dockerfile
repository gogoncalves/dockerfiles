FROM python:3
COPY . /app
USER root
RUN apt-get update
RUN apt-get install -y libudev-dev
RUN apt-get install -y openjdk-11-jre-headless 
WORKDIR /app
CMD java -jar consoleApp-1.0-SNAPSHOT-jar-with-dependencies.jar