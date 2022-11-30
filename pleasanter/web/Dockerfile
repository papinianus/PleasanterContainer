FROM mcr.microsoft.com/dotnet/sdk:6.0
USER root

# 必要なツールをビルド
WORKDIR /tmp
RUN apt update \
    && apt install -y \
    locales \
    libgdiplus

RUN apt-get clean \
    && rm -rf /var/apt/cache/* /tmp/* /var/tmp/* \
    && locale-gen ja_JP.UTF-8

RUN echo 'export LANG=ja_JP.UTF-8' >> ~/.bashrc

WORKDIR /web/pleasanter/Implem.Pleasanter
CMD ["dotnet", "Implem.Pleasanter.dll", "--urls=http://0.0.0.0:5000"]