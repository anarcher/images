FROM alpine:3.10

RUN apk add --no-cache bash curl

ARG version

ENV VERSION ${version:-v0.39.0}

RUN curl -sLO https://storage.googleapis.com/skaffold/releases/${VERSION}/skaffold-linux-amd64 && \
    chmod +x skaffold-linux-amd64 && mv skaffold-linux-amd64 /usr/local/bin/skaffold

ENTRYPOINT ["bash"]
