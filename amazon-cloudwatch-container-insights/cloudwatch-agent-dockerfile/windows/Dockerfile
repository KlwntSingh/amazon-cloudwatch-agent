FROM mcr.microsoft.com/windows/servercore:ltsc2019

RUN mkdir -p "C:\Program Files\Amazon\AmazonCloudWatchAgent"
RUN mkdir -p "C:\ProgramData\Amazon\AmazonCloudWatchAgent\Configs"
RUN mkdir -p "C:\ProgramData\Amazon\AmazonCloudWatchAgent\Logs"
COPY ../../../build/bin/windows_amd64/amazon-cloudwatch-agent.exe "C:\Program Files\Amazon\AmazonCloudWatchAgent"

COPY amazon-cloudwatch-agent.toml "C:\ProgramData\Amazon\AmazonCloudWatchAgent"
COPY common-config.toml "C:\ProgramData\Amazon\AmazonCloudWatchAgent"
COPY env-config.json "C:\ProgramData\Amazon\AmazonCloudWatchAgent"

ENV RUN_IN_CONTAINER="True"
ENTRYPOINT ["C:\Program Files\Amazon\AmazonCloudWatchAgent\amazon-cloudwatch-agent.exe", "-config", "C:\ProgramData\Amazon\AmazonCloudWatchAgent\\amazon-cloudwatch-agent.toml", "-envconfig", "C:\ProgramData\Amazon\AmazonCloudWatchAgent\\env-config.json" ]
