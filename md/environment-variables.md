# Environment Vraiables

How to get your environment variables setup in your terminal.

Thanks to Matt Fox for this helping with this guide.

## Prerequisites

Make sure you have all these installed:

- VS Pro 2019
  - node
  - git
  - python
  - dotnet
- Git
- Nodejs

## Configuration

- Environment Variables
  - find out where the `.exe` files are for git, node, and python

This is the snippet that Matt Fox provided:

```powershell

$temppath = Get-ItemPropertyValue HKCU:\Environment -Name Path
Set-ItemProperty HKCU:\Environment -Name Path -Value "$temppath;<YOUR_PATH_TO_NODE>"

```

So to get Node to be picked up I modified to here :

```powershell

$temppath = Get-ItemPropertyValue HKCU:\Environment -Name Path
Set-ItemProperty HKCU:\Environment -Name Path -Value "$temppath;C:\Program Files\node-v12.18.0-win-x64"

```

> notice no trailing slash after the folder that contains the exe

Normally restarting the terminal would do the trick but in my case I had to log out and back in for it to work for me.

Here is where Git and Python were located:

```powershell

$temppath = Get-ItemPropertyValue HKCU:\Environment -Name Path
Set-ItemProperty HKCU:\Environment -Name Path -Value "$temppath;C:\Program Files\Git\bin"


```

```powershell

$temppath = Get-ItemPropertyValue HKCU:\Environment -Name Path
Set-ItemProperty HKCU:\Environment -Name Path -Value "$temppath;C:\Program Files (x86)\Microsoft Visual Studio\Shared\Python37_64"

```

## Troubleshooting

To check your work you can run this:

```powershell
Get-ItemPropertyValue HKCU:\Environment -Name Path

# It will return something like this

C:\Users\frank.s.pigeon3\AppData\Local\Microsoft\WindowsApps;C:\Program Files\node-v12.18.0-win-x64;C:\Program Files\Git\bin

```

If you mess up and want to override the env path you can run this:

```powershell

Set-ItemProperty HKCU:\Environment -Name Path -Value "C:\Users\frank.s.pigeon3\AppData\Local\Microsoft\WindowsApps;C:\Program Files\node-v12.18.0-win-x64"

```

> Without the `$temppath` it will overwrite the current value instead of appending

Remember to logoff and log back in to get the env to work. Nothing is needed to get `git-bash` working. If it works in PowerShell, it will work in Git Bash.
