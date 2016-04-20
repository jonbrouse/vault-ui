FROM alpine:3.2

ENV CONSUL_VERSION 0.6.4
ENV UI_VERSION 0.6.4

RUN apk add --update ca-certificates curl unzip && \
    rm -rf /var/cache/apk/*

#RUN bash -c 'mkdir -p /consul/{data,conf.d,ui}'
RUN mkdir -p /consul/data

COPY assets/conf.d /consul/conf.d

WORKDIR /consul

RUN curl -O https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip && \
    unzip consul_${CONSUL_VERSION}_linux_amd64.zip && \
    rm -rf ${CONSUL_VERSION}_linux_amd64.zip && \
    chmod +x /consul/consul && \
    curl -O https://releases.hashicorp.com/consul/${UI_VERSION}/consul_${UI_VERSION}_web_ui.zip && \
    unzip consul_${UI_VERSION}_web_ui.zip -d ui && \
    rm -rf consul_${UI_VERSION}_web_ui.zip

EXPOSE 53 8300 8400 8500

ENTRYPOINT ["/consul/consul"]
