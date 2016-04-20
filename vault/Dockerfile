FROM alpine

RUN apk add --update curl unzip && \
    rm -rf /var/cache/apk/*

ENV HOME_DIR=/vault \
    VERSION=0.5.2

RUN mkdir -p ${HOME_DIR}

WORKDIR ${HOME_DIR}

COPY assets/conf.d ${HOME_DIR}/conf.d

RUN curl -O https://releases.hashicorp.com/vault/${VERSION}/vault_${VERSION}_linux_amd64.zip && \
    unzip vault_${VERSION}_linux_amd64.zip && \
    rm -rf vault_${VERSION}_linux_amd64.zip

EXPOSE 8200

ENTRYPOINT ["/vault/vault"]

