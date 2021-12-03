FROM golang:1.17 AS gobuilder
WORKDIR /building
ADD . /building/
RUN go build -o /building/backend main.go

FROM alpine:3.15.0
RUN mkdir /server
WORKDIR /server/
COPY --from=gobuilder /building/backend ./
ENTRYPOINT "/server/backend"