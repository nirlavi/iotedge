ARG base_tag=1.0.0-preview011-linux-arm64v8
FROM azureiotedge/azureiotedge-module-base:${base_tag}

ARG EXE_DIR=.

ENV MODULE_NAME "TemperatureFilter.dll"

WORKDIR /app

COPY $EXE_DIR/ ./

USER moduleuser

CMD echo "$(date --utc +"%Y-%m-%d %H:%M:%S %:z") Starting Edge Agent" && \
    exec /usr/bin/dotnet TemperatureFilter.dll
