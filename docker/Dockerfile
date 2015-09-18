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

# Add in jq to the deault environment
RUN curl -sk -o /usr/local/bin/jq "https://s3.amazonaws.com/github-cloud/releases/5101141/65ac1c64-43ac-11e5-9195-46846013b9a3?response-content-disposition=attachment%3B%20filename%3Djq-linux64&response-content-type=application/octet-stream&AWSAccessKeyId=AKIAISTNZFOVBIJMK3TQ&Expires=1442590830&Signature=Kpyq067MWZN%2Bz2YCjnvyae6bxjo%3D" && chmod a+x /usr/local/bin/jq

# Customize prompt
RUN echo export PS1=\""\[\e[32;4m\]agave-cli\[\e[0m\]:\u@\h:\w$ "\" >> /root/.bashrc
