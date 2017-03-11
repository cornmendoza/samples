.NET Core 1.1.1 Simple Web Application

> dotnet restore

> dotnet publish --configuration Release

Publish using the command line:
> cf push dotnetweb11 -b https://github.com/cloudfoundry-community/dotnet-core-buildpack.git -p ./bin/Release/netcoreapp1.1/publish
