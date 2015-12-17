FROM java:1.8.0_60-b27
MAINTAINER Edwin Steiner <edwin.steiner@inventage.com>

# Install unzip
RUN apt-get update -qq && apt-get install -y unzip && rm -rf /var/lib/apt/lists/*

ENV GRADLE_VERSION 2.8

WORKDIR /usr/bin
RUN curl -sLO https://services.gradle.org/distributions/gradle-$GRADLE_VERSION-all.zip && \
    unzip gradle-$GRADLE_VERSION-all.zip && \
    rm -f gradle-$GRADLE_VERSION-all.zip && \
    ln -s gradle-$GRADLE_VERSION gradle

ENV GRADLE_HOME /usr/bin/gradle
ENV PATH $PATH:$GRADLE_HOME/bin

RUN mkdir /app
WORKDIR /app

ENTRYPOINT ["gradle"]
CMD ["-version"]