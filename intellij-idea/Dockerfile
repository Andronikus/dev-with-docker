FROM eclipse-temurin:17


RUN apt-get update && \
    apt-get install --no-install-recommends -y && \
    apt-get install -y gcc openssh-client libxtst-dev libxext-dev libxrender-dev libfreetype6-dev libfontconfig1 libgtk2.0-0 libxslt1.1 libxxf86vm1 && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -ms /bin/bash developer

ARG IDEA_VERSION=2022.3
ARG IDEA_BUILD=${IDEA_VERSION}.3
ARG IDEA_SORCE=https://download.jetbrains.com/idea/ideaIC-${IDEA_BUILD}.tar.gz
ARG IDEA_LOCAL_DIR=.IdeaIC${IDEA_VERSION}

WORKDIR /opt/idea

RUN curl -fsSL $IDEA_SORCE -o /opt/idea/installer.tgz && tar --strip-components=1 -xzf installer.tgz && rm installer.tgz

USER developer

ENV HOME /home/developer

# RUN mkdir /home/developer/.Idea && ls -sf /home/developer/.Idea /home/developer/$IDEA_LOCAL_DIR

CMD ["/opt/idea/bin/idea.sh"]