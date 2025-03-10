FROM mcr.microsoft.com/dotnet/aspnet:9.0 AS base
USER $APP_UID
WORKDIR /app
EXPOSE 8080
EXPOSE 8081

FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src
COPY ["TreasureHunt.Api/TreasureHunt.Api.csproj", "TreasureHunt.Api/"]
RUN dotnet restore "TreasureHunt.Api/TreasureHunt.Api.csproj"
COPY . .
WORKDIR "/src/TreasureHunt.Api"
RUN dotnet build "TreasureHunt.Api.csproj" -c $BUILD_CONFIGURATION -o /app/build

FROM build AS publish
ARG BUILD_CONFIGURATION=Release
RUN dotnet publish "TreasureHunt.Api.csproj" -c $BUILD_CONFIGURATION -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "TreasureHunt.Api.dll"]
