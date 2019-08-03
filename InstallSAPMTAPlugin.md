## Configure Local Envioronment
### MTA Pulgin 
Multi-Target Application Cloud Foundry CLI Plugin (CF MTA Plugin)
The Multi-Target Application Cloud Foundry CLI Plugin is used to perform operations on multi-target applications (MTAs) such as deploying, removing, viewing, etc.

Download from https://tools.hana.ondemand.com/#cloud

More information on how to install the plugins see Using CF CLI Plugins:https://github.com/cloudfoundry-incubator/multiapps-cli-plugin

Install command:
```
$cf install <path-to-the-plugin> -f
```

Download logs of multi-target app operation:
```
$cf dmol -i <operation_id>
```

### MTA Builder
 The multi-target application archive builder is a standalone command-line tool that builds a deployment-ready multi-target application (MTA) archive .mtar file from the artifacts of an MTA project according to the project’s MTA development descriptor (mta.yaml file).
The archive builder is used on a file system independently of the development environment in which the application project has been created. The build process and the resulting MTA archive depend on the target platform on which the archive is deployed.
The currently supported target platforms are SAP Cloud Platform (both the Neo and Cloud Foundry environments) and SAP HANA XS advanced model.
Each module of an MTA project is built using the build technology that is either associated with the module type by default or is configured explicitly. The archive builder is Java-based, currently supported on Windows and Linux.

Download from https://tools.hana.ondemand.com/#cloud

More Informaiton, see the [Multi-target Application Archive Builder user guide](https://help.sap.com/viewer/58746c584026430a890170ac4d87d03b/Cloud/en-US/9f778dba93934a80a51166da3ec64a05.html)

builde .mtar 
```
java -jar mta_archive_builder-1.1.19.jar --build-target CF --mtar ./target/CalmMTA.mtar build
```