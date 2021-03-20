FROM debian:stable-slim
EXPOSE 8080
WORKDIR /backend

# install prerequisites
RUN apt-get update && apt-get install -y curl
RUN rm -rf /usr/local/go && curl -sL https://golang.org/dl/go1.15.10.linux-amd64.tar.gz | tar -C /usr/local -xzf -
ENV PATH=$PATH:/usr/local/go/bin

# copy the project to the image
COPY . .

# build the project
RUN go build

ENV REQUEST_ORIGIN=http://localhost:5000
CMD ["./server"]
