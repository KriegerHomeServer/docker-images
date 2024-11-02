ARG BUILDPLATFORM
FROM ${BUILDPLATFORM}alpine:3.20

ARG TARGETOS
ARG TARGETARCH

ARG KUBE_VERSION
ARG HELM_VERSION
ARG YQ_VERSION
ARG ARGO_VERSION

RUN apk -U upgrade \
    && apk add --no-cache ca-certificates bash git openssh curl gettext jq \
    && wget -q https://dl.k8s.io/release/v${KUBE_VERSION}/bin/${TARGETOS}/${TARGETARCH}/kubectl -O /usr/local/bin/kubectl \
    && wget -q https://get.helm.sh/helm-v${HELM_VERSION}-${TARGETOS}-${TARGETARCH}.tar.gz -O - | tar -xzO ${TARGETOS}-${TARGETARCH}/helm > /usr/local/bin/helm \
    && wget -q https://github.com/mikefarah/yq/releases/download/v${YQ_VERSION}/yq_${TARGETOS}_${TARGETARCH} -O /usr/local/bin/yq \
    && wget -q https://github.com/argoproj/argo-cd/releases/download/v${ARGO_VERSION}/argocd-${TARGETOS}-${TARGETARCH} -O /usr/local/bin/argocd \
    && chmod +x /usr/local/bin/kubectl /usr/local/bin/helm /usr/local/bin/yq /usr/local/bin/argocd \
    && mkdir /work \
    && chmod g+rwx /work /root

WORKDIR /work

CMD bash