FROM golang:latest as build-stage
WORKDIR /app
COPY main.go .
RUN go build -ldflags "-w" main.go


FROM scratch
WORKDIR /app
COPY --from=build-stage /app/main .
CMD [ "./main" ]