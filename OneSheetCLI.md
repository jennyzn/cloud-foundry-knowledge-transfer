# One Sheet Cloud Foundry CLI
This is a summary for ofen used CLI targeting for SAP developers to search and learn.
## Cloud Foundry Native CLI
### Basics
+ **API selection** ```cf api```

+ **Login** ```cf login``` 

+ **Check/Select target**  ```cf target [-o ORG] [-s SPACE]``` 

### Service Management
+ **List sercice & plans** `cf marketplaces`

+ **List services in current space** `cf services`

+ **New service instance** `cf create-service SERVICE PLAN SERVICE_INSTANCE [-c PARAMETERS_AS_JSON] [-t TAGS]`

+ **Show service information** `cf service SERVICE_INSTANCE`

+ **Bind service to app** ` cf bind-service APP_NAME SERVICE_INSTANCE [-c PARAMETERS_AS_JSON] [--binding-name BINDING_NAME]`

+ **Unbind service** ` cf bind-service APP_NAME SERVICE_INSTANCE`

+ **Update service** `cf update-service SERVICE_INSTANCE [-p NEW_PLAN] [-c PARAMETERS_AS_JSON] [-t TAGS]`

	Example: `cf update-service mydb -b '{"ram_gb": 4}'`

+ **Delete service instance** `cf delete-service SERVICE_INSTANCE [-f]`
### Application Management
+ **List applications** `cf apps`

	list all application in the current space

+ **Display app information** `cf app APP`

	Display health status of the applicaiton instance

+ **push app to CF** ```cf push```

+ **Scale application** ` cf scale APP_NAME [-i INSTANCES] [-k DISK] [-m MEMORY] [-f]`

+ **Start/stop/restart** `cf start/stop/restart APP`

+ **Delete app** `cf delete APP [-f] [-r]`
## SAP MTA (Multi-Target Applicaiton) Plugin CLI
+ **Build MTA artifact (.mtar)** `java -jar [path to mta.jar] –-[option][=arguments] [command]` 

	Example: `java -jar mta_archive_builder-1.1.7.jar --build-target CF --mtar ./target/tkm-srv.mtar build`

## Buid and deploy CAP-based application
### Prerequisites
How to install? See [InstallSAPPlugin.md](./InstallSAPPlugin.md)

1.MTA Plugin

2.MTA Builder

3.CDS Builder
### Steps
1. Under root folder, build all your CDS files. Run:
```bash
cds build
```

2. Under "srv", build your Spring Boot application. Run:
```bash
mvn package
```

3. Under root folder, build the MTA artifact. Run:
```bash
java -jar mta_archive_builder-1.1.19.jar --build-target CF --mtar ./target/tkm-srv.mtar build
```

4. Under root folder, deploy the MTA artifact. Run:
```bash
cf deploy target/tkm-srv.mtar
```
