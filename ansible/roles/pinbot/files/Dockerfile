FROM golang:1.9.2
MAINTAINER Lars Gierth <larsg@systemli.org>

ENV GOPATH=/go \
    REPO_PATH=github.com/ipfs/pinbot-irc
COPY . $GOPATH/src/$REPO_PATH

RUN cd $GOPATH/src/$REPO_PATH \
    && go build -o /bin/pinbot $REPO_PATH

VOLUME     [ "/pinbot" ]
WORKDIR    /pinbot
ENTRYPOINT [ "/bin/pinbot" ]
CMD        [  ]

# XXX pending this fix: https://github.com/ansible/ansible-modules-core/pull/2258
EXPOSE 12345
