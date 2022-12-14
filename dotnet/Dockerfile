####
# Base
###
FROM mcr.microsoft.com/dotnet/sdk:6.0.403-alpine3.16 AS base

WORKDIR /build
RUN dotnet --version > dotnet_version

####
# Service
###
FROM mcr.microsoft.com/dotnet/aspnet:6.0.12-alpine3.16 AS service
RUN addgroup -g 1000 app \
    && adduser -u 1000 -G app -s /bin/sh -D app

WORKDIR /app
COPY --from=base --chown=1000 build /app
