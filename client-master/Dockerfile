FROM tomcat:9-jre10

RUN apt-get update && \
    apt-get install -y \
      curl \
      vim \
      maven \
    #   openjdk-10-jdk \
  && rm -rf /var/lib/apt/lists/*

ENV CATALINA_OPTS="-Xmx700m --add-modules java.xml.bind,java.xml.ws --add-exports java.base/jdk.internal.ref=ALL-UNNAMED"

ADD conf/ROOT.xml /usr/local/tomcat/conf/Catalina/localhost/ROOT.xml
ADD logging.properties /usr/local/tomcat/conf/logging.properties
CMD ["catalina.sh", "run"]