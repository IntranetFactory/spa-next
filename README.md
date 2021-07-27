# Platform Deploy

This repo contains templates to setup the Digital Assistant Container Edition.

## Container Source

You need to have access to the registry.gitlab.com/adenin-projects/platform-deploy container. Please contact your account manager if you need to be authorized to access that container registry.

## Running on Windows

To run the container on Windows WSL2 and Docker Desktop on Windows is needed. Please see https://docs.microsoft.com/en-us/windows/wsl/install-win10 for wsl2 setup instructions.

>On initial run, you are required to set some global VM settings in Windows Subsystem for Linux. Type the command `wsl` into a command prompt and once inside the Linux shell, execute `sudo sysctl -w vm.max_map_count=262144`


## docker-sandbox

The docker-sandbox folder contains a complete sandbox configuration with the Digital Assistant server, Postgresql database and Elastic Search servers.

`docker compose up` starts the environment, creates new databases and a new, empty tenant. The default server url is http://localhost:9903


## System Administration

The System Administration Area contains global server settings.

The default login for the System Administration area is 

Username: `admin`    
Password: `adenin*123`



## Tenant Administration

The platform can manage multiple tenants. A new installation contains one default tenant

The default login for the Tenant Administration area is 

Username: `admin@tenant.com`    
Password: `adenin*123`


## Initial Configuration

The following configuration information needs to be added to a fresh database:


### Search 

Go to Settings (http://localhost:9903/App/BusinessObjects?entitytype=setting) and find the record with the name `AzureSearch`. Select _Service Provider_ `Elastic`, _Elastic Host_ `elasticsearch`
