FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
WORKDIR /app
EXPOSE 5122

ENV ASPNETCORE_URLS=http://+:5122

# Creates a non-root user with an explicit UID and adds permission to access the /app folder
# For more info, please refer to https://aka.ms/vscode-docker-dotnet-configure-containers
RUN adduser -u 5678 --disabled-password --gecos "" appuser && chown -R appuser /app
USER appuser

FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["HelloAspNetCore.csproj", "./"]
RUN dotnet restore "./HelloAspNetCore.csproj"
COPY . .
# WORKDIR "/src/HelloAspNetCore"
RUN dotnet build "HelloAspNetCore.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "HelloAspNetCore.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "HelloAspNetCore.dll"]
