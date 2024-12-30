# escape=`

FROM mcr.microsoft.com/windows/servercore:ltsc2022

# This is a workaround for nanoserver where not possible to set PATH using setx or similar
# Some failed attempts below; someone could fix these!
ENV PATH="C:\Windows\system32;C:\Windows;C:\Git\bin;C:\Git\usr\bin;C:\Python;C:\Python\Scripts;C:\Gnuplot\bin"

RUN `
    # Download all files
    curl -fSLo Git-Setup.exe http://host.docker.internal/files/Git-2.47.1-64-bit.exe `
    && curl -fSLo Python-Setup.exe http://host.docker.internal/files/python-3.13.0-amd64.exe `
    && curl -fSLo Gnuplot-Setup.exe http://host.docker.internal/files/gp467-win64-setup.exe `
    `
    # Install Git
    && Git-Setup.exe /VERYSILENT /SUPPRESSMSGBOXES /NORESTART /DIR="C:\\Git" `
    && setx /M PATH "%PATH%;C:\\Git\\bin;C:\\Git\\usr\\bin" `
    # Install Python
    && Python-Setup.exe /quiet InstallAllUsers=1 PrependPath=0 Include_test=0 TargetDir="C:\\Python" `
    && setx /M PATH "%PATH%;C:\\Python;C:\\Python\\Scripts" `
    # Install Gnuplot
    && Gnuplot-Setup.exe /VERYSILENT /SUPPRESSMSGBOXES /NORESTART /DIR="C:\\Gnuplot" `
    && setx /M PATH "%PATH%;C:\\Gnuplot\\bin" `
    `
    # Download miss files
    && curl -fSLo "C:\\Gnuplot\\bin\\hhctrl.ocx" http://host.docker.internal/files/hhctrl.ocx `
    `
    # Install pip
    && python -m ensurepip --upgrade `
    && python -m pip install --upgrade pip `
    # Install gitstats
    && pip install gitstats `
    `
    # Clean up temporary files
    && del *.exe `
    && del /Q /S %TEMP%\* `
