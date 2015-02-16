FROM ubuntu:14.04

#install wget and other dependencies
RUN apt-get update
RUN apt-get -y install wget git zip openjdk-7-jre

#install scala
RUN /bin/bash -l -c "wget http://downloads.typesafe.com/scala/2.11.5/scala-2.11.5.tgz"

RUN /bin/bash -l -c "tar xfvz scala-2.11.5.tgz"

RUN /bin/bash -l -c "mkdir -p /app/blackjack"

RUN /bin/bash -l -c "git clone https://github.com/cavenator/BlackJack.git /app/blackjack"

ENV SCALA_HOME /scala-2.11.5
ENV PATH $PATH:$SCALA_HOME/bin

WORKDIR /app/blackjack

RUN /bin/bash -l -c "scalac *.scala"

ENTRYPOINT ["scala"]

CMD ["Main"]
