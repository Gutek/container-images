FROM mcr.microsoft.com/azure-sql-edge:latest

USER root
# this does not work with docker image
# ENV MSSQL_PACKAGE=/var/opt/mssql/backup/

# Install dependencies and sqlpackage
# sqlpackage will be located in /opt/mssql-tools/bin/
RUN apt-get update && \
    apt-get install -y wget unzip libunwind8 && \
    wget -O sqlpackage.zip https://go.microsoft.com/fwlink/?linkid=2157202 && \
    unzip sqlpackage.zip -d /opt/mssql-tools/bin/ && \
    chmod +x /opt/mssql-tools/bin/sqlpackage && \
    rm sqlpackage.zip

USER mssql