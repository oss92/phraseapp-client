FROM ubuntu:18.04

RUN dpkg --add-architecture i386
RUN apt-get update && apt-get install -y --no-install-recommends curl ca-certificates wine-stable wine32 xvfb

ENV WINEDEBUG fixme-all
ENV WINEARCH win32

# # Install Inno Setup binaries
RUN curl -SL "https://github.com/jrsoftware/issrc/releases/download/is-5_6_1/innosetup-5.6.1.exe" -o is.exe
RUN xvfb-run wine wineboot --init \
        && xvfb-run -e /dev/stdout wine is.exe /VERYSILENT /SUPPRESSMSGBOXES /NORESTART

