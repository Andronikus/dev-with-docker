FROM mcr.microsoft.com/dotnet/sdk:8.0

ENV DOTNET_USE_POLLING_FILE_WATCHER=true \
    DOTNET_CLI_TELEMETRY_OPTOUT=1 \
    DOTNET_NOLOGO=true

WORKDIR /app

# Install dev tools
RUN apt-get update && apt-get install -y \
    git curl unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 5000 5001

CMD [ "bash" ]