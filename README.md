# Ngrok Extensions for Visual Studio

[![Build status](https://ci.appveyor.com/api/projects/status/mi2kn7oaluldhuyo/branch/master?svg=true)](https://ci.appveyor.com/project/dprothero/ngrokextensions/branch/master)

## Looking for new owner

### 📣 This project is looking for a new owner. Please contact me if you are interested. 📣

## Description

This extension allows you to use [ngrok](https://ngrok.com) right from within Visual Studio.
It will start a tunnel for each web application that is part of your solution.

Has been tested in Visual Studio 2015, 2017, and 2019.

## Installation

### From Visual Studio

Get it from the [Visual Studio Gallery](https://visualstudiogallery.msdn.microsoft.com/56a642ed-a5e0-4044-8735-740d36912c5e).
From within Visual Studio:

1. Select Tools... Extensions and Updates...
2. Click "Online" and select the "Visual Studio Gallery" along the left-hand side of the window.
3. Type "ngrok" into the search box in the upper right.
4. Click the "Download" button on the extension in the search results.

### Build from Source

1. Clone this repo
2. Open with Visual Studio 2017 and build a `Release` build
3. Find the .vsix file in the `bin\Release` folder
4. Double-click the .vsix file to install

## Usage

Currently, usage is super-simple. All you need to do is open a solution with
one or more web projects and then choose "Start ngrok Tunnel" from the "Tools"
menu.

![Menu item](https://raw.githubusercontent.com/dprothero/NgrokExtensions/master/docs/img/menu-item.png)

### Custom ngrok Subdomains

If you have a paid ngrok account, you can make use of custom subdomains with
this extension.

Specify the subdomain you would like it to use in a `ngrok.subdomain` key
in the `appSettings` section of your `web.config` file like so:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <appSettings>
    <add key="ngrok.subdomain" value="my-cool-app"/>
    ... more appSettings keys omitted ...
  </appSettings>
  ... more config omitted ...
</configuration>
```

#### Custom ngrok Subdomains with ASP.NET Core or Azure Functions

If you are using an ASP.NET Core or Azure Functions project and want to test locally, you can set the
`ngrok.subdomain` key in the `appsettings.json` file like so:

```json
{
  "IsEncrypted": false,
  "Values": {
    "ngrok.subdomain": "my-cool-app",
    ... more app settings omitted ...
  }
}
```

You can also set this value in a `secrets.json` file as [described here](https://docs.microsoft.com/en-us/aspnet/core/security/app-secrets?tabs=visual-studio).

## Feedback and Contribution

This is a brand new extension and would benefit greatly from your feedback
and even your code contribution.

If you find a bug or would like to request a feature,
[open an issue](https://github.com/dprothero/NgrokExtensions/issues).

To contribute, fork this repo to your own GitHub account. Then, create a
branch on your own fork and perform the work. Push it up to your fork and
then submit a Pull Request to this repo. This is called [GitHub Flow](https://guides.github.com/introduction/flow/).

## Change Log

* v0.9.13 - Add support for https.
* v0.9.12 - Add support for Visual Studio 2019.
* v0.9.11 - Fix ngrok installer after ngrok download page changed.
* v0.9.10 - Allow settings override in secrets.json. Thanks @ChristopherHaws!
* v0.9.9 - Bug fixes. Find projects within Solution folders.
* v0.9.8 - Bug fixes. Automatically install ngrok.exe if not found.
* v0.9.7 - Support for ASP.NET Core projects. Thanks @ahanoff!
* v0.9.6 - Added support for Visual Studio 2017.
* v0.9.5 - Added support for Azure Function projects.
* v0.9.4 - Added support for Node.js projects.
* v0.9.3 - Fix crash when decimal values in ngrok's JSON response.
* v0.9.2 - Allow customizing location of ngrok.exe.
* v0.9.1 - Initial Release

* * *

Licensed under the MIT license. See the LICENSE file in the project root for more information.

Copyright (c) 2019 David Prothero
