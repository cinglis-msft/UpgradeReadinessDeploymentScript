# The Upgrade Readiness Deployment Script

This script is discontinued for public use due to the retirement of Upgrade Readiness on January 31, 2020. However, it is a useful troubleshooting tool to ensure devices are configured correctly to send telemetry to Update Compliance.

## How this script is organized

This script is organized into two buckets: **Deployment** and **Pilot**. Both directories have the same key files -- `ConfigScript.ps1` and `RunConfig.bat`. You configure `RunConfig.bat` according to the directions in the `.bat` itself, which will then execute `ConfigScript.ps1` with the parameters entered to `RunConfig.bat`. 

* The **Deployment** portion of the script is intended to be deployed at-scale. It runs quietly, under the assumption that all devices are configured uniformly. However, 
* the **Pilot** portion of the script is intended to be tested on a limited number of devices and for troubleshooting. It is verbose, and saves logs according to the `logPath` variable in `RunConfig.bat`. The Pilot directory also has a Diagnostics directory with additional troubleshooting `.exe` files.


## How to use this script

When using this in the context of troubleshooting, use `Pilot`. Enter `RunConfig.bat`, and additionally do the following:

1. Configure `logPath` where you want the Logs to be output.
2. Configure `commercialIDValue` to your Commercial ID.
3. Run the script
4. Examine the Logs output for any issues. If there are no issues, then all devices with a similar configuration and network profile are ready for the Deployment script. 
5. If there are issues, gather the Logs and provide them to Support.
