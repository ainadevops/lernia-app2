FROM registry.access.redhat.com/ubi9:latest AS builder

RUN dnf install -y git-core golang make
RUN git clone https://github.com/ainadevops/lernia-app2.git && cd lernia-app/src && make


FROM registry.access.redhat.com/ubi9-minimal:latest
COPY --from=builder /lernia-app/src/lernia /lernia
CMD ["/lernia"]


