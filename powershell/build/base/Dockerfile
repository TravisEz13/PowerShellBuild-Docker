# escape=`
ARG fromTag=ltsc2016
ARG WindowsServerCoreRepo=mcr.microsoft.com/windows/servercore

# Use server core as an installer container to extract PowerShell,
# As this is a multi-stage build, this stage will eventually be thrown away
FROM ${WindowsServerCoreRepo}:${fromTag} AS installer-env

RUN powershell `
        -NoLogo `
        -NoProfile `
        -Command "Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))"
