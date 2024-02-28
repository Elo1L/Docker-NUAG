FROM --platform=${BUILDPLATFORM} mcr.microsoft.com/dotnet/sdk:7.0 AS builder

ARG TARGETPLATFORM
ARG TARGETARCH
ARG BUILDPLATFORM

RUN echo $TARGETPLATFORM
RUN echo $TARGETARCH
RUN echo $BUILDPLATFORM

WORKDIR /source

COPY . .

RUN dotnet restore -a $TARGETARCH
RUN dotnet publish -c release -o /app -a $TARGETARCH --self-contained false --no-restore


FROM mcr.microsoft.com/dotnet/runtime:7.0
COPY --from=builder /app ./app
CMD dotnet ./app/Worker.dll