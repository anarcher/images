FROM docker:stable

RUN apk add --no-cache bash curl

ARG version

ARG kustomize_version

ENV VERSION ${version:-v0.39.0}

ENV KUSTOMIZE_VERSION ${kustomize_version:-v3.2.1}

RUN curl -sLO https://storage.googleapis.com/skaffold/releases/${VERSION}/skaffold-linux-amd64 && \
    chmod +x skaffold-linux-amd64 && mv skaffold-linux-amd64 /usr/local/bin/skaffold

RUN curl -Lo kustomize https://github.com/kubernetes-sigs/kustomize/releases/download/v{$VERSION}/kustomize_${VERSION}_linux_amd64 && chmod +x kustomize && mv kustomize /usr/local/bin

ENTRYPOINT ["bash"]
