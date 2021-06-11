# K-12 Skillet

## Overview

The K-12 Skillet is intended for K-12 educational deployment configuration as an Internet Gateway
using 2 zones, the untrust zone as a dhcp-client, and Safe Search configurations (Decryption, DNS Proxy, and DNS restrictions).

The security policy provides for outbound policies using IronSkillet best practice security profiles and groups.

### New Skillet Framework 

The K-12 Skillet utilizes Git submodules in order to pull external skillets into this repository for its use. This 
K-12 solution utilizes the skillets located in the [IronSkillet Components](https://github.com/PaloAltoNetworks/ironskillet-components), 
[SLED Components](https://github.com/annabarone/SLED-components), [PAN-OS Upgrade/Downgrade](https://gitlab.com/panw-gse/tech-library/deploy/panos-ansible-upgrade-downgrade),
and [PAN-OS Config Elements](https://gitlab.com/panw-gse/tech-library/configure/panos-config-elements) repositories. Since 
the submodules specifically point to a commit in the external repository's history, the K-12 solution 
can stay up-to-date by simply updating the commit references. 

> **NOTE**: Updating the K-12 repository on your local machine using a `git pull origin master` will not update the 
> submodule content. If you are hoping to update the submodule references to point to the latest commits in the external
> repositories' history, you will need to run `git submodule update --remote --merge`. This command will merge all submodule
> changes into your local K-12 repo.

For more information about the new skillet framework, please see the [Skillet Builder documentation](https://skilletbuilder.readthedocs.io/en/latest/index.html).

For more guidance on creating playlist skillets and using submodules, please see the [Skillet Builder Includes Tutorial](https://skilletbuilder.readthedocs.io/en/latest/index.html).

## Requirements

* PAN-OS 10.X
* Threat, URL, and Wildfire subscriptions
* PanHandler Version 4.5+

### K-12 Skillet and PanHandler

K-12 Skillet is designed to be used with the PanHandler application to API
load structured configurations. It also captures web form data to semi-customize
the configuration for local use.

See the [PanHandler documentation](https://panhandler.readthedocs.io) for instructions on installing,
updating, navigating, and using PanHandler.


## Features Included

The following features are included in the K-12 Quickplay Solution:

    * Builds on the Iron Skillet configurations
    * Dynamic configuration based on the desired Safe Search deployment:
        * Transparent - SSL inspection with NGFW enforced Safe Search
        * DNS-Proxy - NGFW responds to Google and Bing search engine requests with Safe Search only server IPs
        * Local DNS CNAME - Limits outbound DNS requests to sanctioned internal DNS servers with Google and Bing Safe Search configurations
    * Optional country block - Only allows IPs from US, Mexico, Canada, and cloud providers (based on EDL)
    * K-12 Reports
    * Targeted decryption policies to help enable SSL-Decryption adoption and limit risk


## How to Use the K-12 Solution

It is assumed that you have PanHandler Version 4.5+ already installed. Follow these instructions for running 
the K-12 Solution:

  1. Import this repository into PanHandler
  2. In your K-12 Repository Details page, click on the *K-12 Educational Deployment Full Workflow* workflow skillet
  3. Input your NGFW IP, admin credentials, and PAN-OS software version
  4. Input the sub-skillets you need configured, more information about the workflow menu options below
  5. Click **Submit** to start the workflow execution. You will need to input additional information for the 
      IronSkillet and K-12 Configuration Skillets.

### Workflow Menu Options

In addition to inputting your Next-Gen Firewall's information, you will need to check the boxes for 
the skillets you wish to execute. Those skillets perform the following actions: 

    1. Load an clean, 'out-of-the-box' baseline configuration while saving existing admin credentials and mgt interface configurations
    2. Perform a content update
    3. Configure the latest IronSkillet specific to your PAN-OS version
    4. Configure the K-12 Solution

> **NOTE**: You must have IronSkillet configured on your NGFW before loading the K-12 solution since many K-12 
> configuration elements depend on IronSkillet elements. 


## Support Policy
The code and templates in the repo are released under an as-is, best effort, support policy.
These scripts should be seen as community supported and Palo Alto Networks will contribute
our expertise as and when possible. We do not provide technical support or help in using
or troubleshooting the components of the project through our normal support options
such as Palo Alto Networks support teams, or ASC (Authorized Support Centers) partners
and backline support options. The underlying product used (the VM-Series firewall)
by the scripts or templates are still supported, but the support is only for the
product functionality and not for help in deploying or using the template or script itself.
Unless explicitly tagged, all projects or work posted in our GitHub repository
(at https://github.com/PaloAltoNetworks) or sites other than our official Downloads page
on https://support.paloaltonetworks.com are provided under the best effort policy.
