# K-12 Skillet


## Overview

The K-12 Skillet is indented for K-12 educational deployment configuration as an Internet Gateway
using 2 zones, the untrust zone as a dhcp-client, and Safe Search configurations (Decyption, DNS Proxy, and DNS restrictions).

The security policy provides for outbound policies using IronSkillet
best practice security profiles and groups.


## K-12 Skillet and panhandler

K-12 Skillet is designed to be used with the panhandler application to API
load structured configurations. It also captures web form data to semi-customize
the configuration for local use.

[panhandler](https://panhandler.readthedocs.io)

## Known Issues
Before using this Skillet you should download and install the latest Threat package on the target firewall.

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
