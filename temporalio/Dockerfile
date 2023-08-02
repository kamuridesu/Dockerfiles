FROM debian:bullseye-20230725-slim
EXPOSE 7233
EXPOSE 8233
RUN apt-get update && apt-get install curl -y --fix-missing
RUN curl --output /tmp/temporal.tar.gz "https://temporal.download/cli/archive/latest?platform=linux&arch=amd64" \
    && tar -xvf /tmp/temporal.tar.gz \
    && mv temporal /usr/bin/temporal \
    && rm /tmp/temporal.tar.gz
ENTRYPOINT [ "temporal", "server", "start-dev" ]
