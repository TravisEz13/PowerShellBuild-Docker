# escape=`
ARG fromTag=ltsc2019
ARG WindowsServerCoreRepo=mcr.microsoft.com/windows/servercore

# Use server core as an installer container to extract PowerShell,
# As this is a multi-stage build, this stage will eventually be thrown away
FROM ${WindowsServerCoreRepo}:${fromTag} AS installer-env

ADD https://chocolatey.org/7za.exe C:\7za.exe

ADD https://chocolatey.org/api/v2/package/chocolatey/0.10.15 C:\choco.zip

RUN C:\7za.exe x -o"C:\unzip" -bd -y "C:\choco.zip"
