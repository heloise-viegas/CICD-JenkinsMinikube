FROM mcr.microsoft.com/dotnet/sdk:5.0-buster-slim
# mcr.microsoft.com/dotnet/framework/sdk --error --docker hub
# mcr.microsoft.com/dotnet/sdk:5.0-buster-slim
WORKDIR /app
ADD ./ /app
# dotnet restore command uses NuGet to restore dependencies as well as project-specific tools
RUN dotnet restore
# Build a project and its dependencies using Release configuration
# RUN dotnet build -c Release
RUN ls
RUN dotnet clean aspnetapp.sln --configuration Release
RUN dotnet build aspnetapp.sln --configuration Release
# build creates /app/bin/Release/net5.0/aspnetapp.dll
RUN dotnet publish aspnetapp.sln --configuration Release

# works instead of build
# RUN dotnet msbuild -property:Configuration=Release

# publish your code in release mode and save output to publish directory
# RUN dotnet publish -c Release -o /publish   
# COPY . .
ENV ASPNETCORE_URLS=http://+:5000
EXPOSE 5000
ENTRYPOINT ["dotnet", "/app/aspnetapp/bin/Release/net5.0/aspnetapp.dll"]


# ms build
# mcr limitations using that image