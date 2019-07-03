FROM ubuntu:16.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
        apt-get install -y --no-install-recommends \
        ca-certificates curl jq git iputils-ping libcurl3 libicu55 \
        apt-transport-https ca-certificates curl gnupg-agent \
        software-properties-common && \
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
        apt-key add - && \
        add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" && \
        apt-get update && \
        apt-get install -y docker-ce docker-ce-cli containerd.io

WORKDIR /azp

COPY ./start.sh .
RUN chmod +x start.sh

CMD ["./start.sh"]
