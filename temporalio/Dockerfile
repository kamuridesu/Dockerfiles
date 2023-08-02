FROM debian:bullseye-20230725-slim
EXPOSE 7233
EXPOSE 8233
ARG TARGETARCH
RUN apt-get update
RUN apt-get install curl -y --fix-missing || apt --fix-broken install -y
RUN curl --output /tmp/temporal.tar.gz "https://temporal.download/cli/archive/latest?platform=linux&arch=${TARGETARCH}" \
    && tar -xvf /tmp/temporal.tar.gz \
    && mv temporal /usr/bin/temporal \
    && rm /tmp/temporal.tar.gz
ENTRYPOINT [ "temporal", "server", "start-dev", "--ui-ip", "0.0.0.0", "--ip", "0.0.0.0" ]
