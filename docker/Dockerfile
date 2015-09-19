######################################################
#
# Agave CLI Image, customized by iPlant
# Tag: iplantc/agave-cli
#
# https://bitbucket.org/taccaci/agave-environment
#
# This container the Agave CLI and can be used for
# parallel environment testing.
#
# docker run -it -v $HOME/.agave:/root/.agave iplantc/agave-cli bash
#
# Build using
# docker build --rm=true -t iplantc/agave-cli .
#
######################################################

FROM agaveapi/agave-cli:latest
MAINTAINER Matthew Vaughn <vaughn@iplantcollaborative.org>
RUN yum install -y wget which

# Add in jq to the default environment
RUN curl -L -sk -o /usr/local/bin/jq "https://github.com/stedolan/jq/releases/download/jq-1.5/jq-linux64" && chmod a+x /usr/local/bin/jq

# Add jsonpki
RUN git clone https://github.com/mwvaughn/agave-jsonpki.git && cp agave-jsonpki/jsonpki.sh /usr/local/bin/jsonpki.sh && chmod a+x /usr/local/bin/jsonpki.sh && rm -rf agave-jsonpki

# Customize prompt
RUN echo export PS1=\""\[\e[32;4m\]agave-cli\[\e[0m\]:\u@\h:\w$ "\" >> /root/.bashrc
