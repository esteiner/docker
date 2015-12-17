FROM esteiner/jdk:1.8.0_66-b17

ENV MAVEN_MAJOR_VERSION 3
ENV MAVEN_MINOR_VERSION 3
ENV MAVEN_MICRO_VERSION 9

RUN curl -fsSL http://archive.apache.org/dist/maven/maven-$MAVEN_MAJOR_VERSION/$MAVEN_MAJOR_VERSION.$MAVEN_MINOR_VERSION.$MAVEN_MICRO_VERSION/binaries/apache-maven-$MAVEN_MAJOR_VERSION.$MAVEN_MINOR_VERSION.$MAVEN_MICRO_VERSION-bin.tar.gz | tar xzf - -C /usr/share \
  && mv /usr/share/apache-maven-$MAVEN_MAJOR_VERSION.$MAVEN_MINOR_VERSION.$MAVEN_MICRO_VERSION /usr/share/maven \
  && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn

ENV MAVEN_HOME /usr/share/maven

ENTRYPOINT ["mvn"]
CMD ["-h"]