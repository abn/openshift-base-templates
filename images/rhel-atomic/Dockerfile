FROM registry.access.redhat.com/rhel-atomic:7

LABEL name="rhel-atomic" \
    io.openshift.tags="base,os" \
    io.k8s.description="RHEL base image with common packages and certs" \
    io.k8s.display-name="Red Hat Atomic Linux"

COPY assets/certs /etc/pki/ca-trust/source/anchors

RUN update-ca-trust extract \
    && microdnf install \
        --enablerepo=rhel-7-server-rpms \
        --nodocs \
        shadow-utils tar gzip unzip bc which lsof ca-certificates \
    && microdnf clean all