FROM openjdk:11-jdk

WORKDIR /tools

# install tutorbot
RUN git clone https://github.com/simonschiller/tutorbot.git && \
    cd tutorbot && \
    ./gradlew jar

# tutorbot build artifact is runnable from /opt
COPY ./tutorbot.sh /opt/tutorbot

# tutorbot.properties are expected in the same directory as the executable
COPY ./tutorbot.properties /tools/tutorbot/build/libs/

VOLUME ["/submissions", "/reviews"]

ENTRYPOINT [ "/opt/tutorbot" ]
