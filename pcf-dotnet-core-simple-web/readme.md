.NET Core 1.1.1 Simple Web Application

> dotnet restore

> dotnet publish --configuration Release

Modify the generated dotnetweb-1-1.runtimeconfig.json file in the release directory to use with Cloud Foundry until support for .NET Core 1.1.1 is provided

{
  "runtimeOptions": {
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "1.1.0"  <--- Updated from 1.1.1 to 1.1.0 
    },
    "configProperties": {
      "System.GC.Server": true
    }
  }
}

Publish using the command line:
> cf push dotnetweb11 -b https://github.com/cloudfoundry-community/dotnet-core-buildpack.git -p ./bin/Release/netcoreapp1.1/publish
