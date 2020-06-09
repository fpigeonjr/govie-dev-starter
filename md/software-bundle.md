# BTS DEV Bundle 6-9-2020

## Baseline

- [Visual Studio 2019 *PRO*](https://visualstudio.microsoft.com/subscriptions/)
  - Addons: Git, Python, Node, dotnetCore
- [Visual Studio Code *System 64* ](https://code.visualstudio.com/)
- SQL Server Managent Studio 2018
- SharePoint Designer 2013 (x32)
- [Node.JS LTS](https://nodejs.org/en/download/)
- .NET Core
- Python 3 (comes with VS2019)
- [Git](https://git-scm.com/downloads)

## Optional

- Infragistics
- Ultra Compare
- Adobe Creative Cloud 
- Jet Brains Resharper
  - install for `all users`
- [Gatsby](https://www.gatsbyjs.org/docs/gatsby-on-windows/)

## Config

### npm fix

```bash

npm config set registry http://registry.npmjs.org/

```

A user with administrator rights and you must open notepad(Right-click as Administrator) then open the file devenv.exe.config.

### VS2013

`C:\Program Files (x86)\Microsoft Visual Studio 12.0\Common7\IDE\devenv.exe.config` <br/>
(Note: the file shows as devenv.exe with extensions hidden) then add the line(after `<runtime>`.

### VS2017

`C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE\devenv.exe.config`<br/>
Add this line to file after `<runtime>`

```xml

// devenv.exe.config

<runtime>
  // add here
  <enforceFIPSPolicy enabled="false"/>
  // more code
</runtime>

```

### Other

* SW Share `\\139.232.7.71\ameddcs`
* TFS `https://medcoetfs.nasw.ds.army.mil`
* VPN `fshtx.ra.army.mil`
* Printer `\\amcsps2\amcspr361031c`