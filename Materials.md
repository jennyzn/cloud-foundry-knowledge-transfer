Firstly refer to <https://github.wdf.sap.corp/SolmanChina/Template_CAP_Spring_Boot> to install all necessary tools e.g. nodejs, CDS builder, CF CMD plugin for MTA deploy.

## How to create CDS model locally
Refer to the part `APPENDIX 2` of the link below:

<https://blogs.sap.com/2019/01/25/sap-cloud-platform-backend-service-tutorial-0.3-cds-model-creation-tools/>

## How to compile CDS model locally
1. Install node.js version 8 or higher. Execute the following command to check the node version:
```bash
node -v
```
2. Configure the NPM registry by executing the following command:
```bash
npm config set @sap:registry https://npm.sap.com
```
3. Install the CDS command-line tools.
```bash
npm i -g @sap/cds
```
4. Check the installation by running the following command:
```bash
cds --version
```