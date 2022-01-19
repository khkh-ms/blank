### WEBSITE_NODE_DEFAULT_VERSION is not working in Linux.
- `WEBSITE_NODE_DEFAULT_VERSION` is Windows only property. [Click here ](https://docs.microsoft.com/en-us/azure/azure-functions/functions-app-settings#website_node_default_version) for more information. 
- Linux apps should use `LinuxFxVersion` setting. 

### How `linuxFxVersion` is added in an ARM template?
- Linux apps should include a `linuxFxVersion` property under `siteConfig`. If you are just deploying code, the value for this is determined by your desired runtime stack in the format of `runtime|runtimeVersion`.
- If you are deploying a custom container image, you must specify it with `linuxFxVersion` and include configuration that allows your image to be pulled, as in Web App for Containers. Also, set `WEBSITES_ENABLE_APP_SERVICE_STORAGE` to `false`, since your app content is provided in the container itself:
- More information about setting `linuxFxVersion` [using ARM template ](https://docs.microsoft.com/en-us/azure/azure-functions/functions-infrastructure-as-code#create-a-function-app-2) and [using Azure CLI](https://docs.microsoft.com/en-us/azure/azure-functions/set-runtime-version?tabs=azurecli#manual-version-updates-on-linux) is available online. 
