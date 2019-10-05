FROM docker:stable

RUN apk add --no-cache bash curl

ARG version

ARG kustomize_version

ENV VERSION ${version:-v0.39.0}

ENV KUSTOMIZE_VERSION ${kustomize_version:-v3.2.1}

RUN curl -sLO https://storage.googleapis.com/skaffold/releases/${VERSION}/skaffold-linux-amd64 && \
    chmod +x skaffold-linux-amd64 && mv skaffold-linux-amd64 /usr/local/bin/skaffold

RUN curl -sLO https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2F{$KUSTOMIZE_VERSION}/kustomize_kustomize.${KUSTOMIZE_VERSION}_linux_amd64 && mv kustomize_kustomize.${KUSTOMIZE_VERSION}_linux_amd64 kustomize && chmod +x kustomize && mv kustomize /usr/local/bin/kustomize

ENTRYPOINT ["bash"]
