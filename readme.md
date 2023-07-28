## Summary:
This repo is a collection of Ansible playbook yaml files designed for automating the onboarding of applications into Dynatrace.  These playbooks were written and tested on Red Hat Ansible Tower, but should work with other platforms such as vanilla Ansible and AWX.

## Dynatrace Support
For the latest support of Ansible with Dynatrace, please refer to the Dynatrace documentation:\
https://www.dynatrace.com/support/help/shortlink/oneagent-ansible

## Dynatrace Monaco - Monitoring as Code
For the latest Dynatrace configuration management, consider integrating Ansible with Monaco:\
https://www.dynatrace.com/support/help/shortlink/configuration-as-code 

## Playbooks:
* dt-oneagent-install-linux.yml - Installs Dynatrace OneAgent (or upgrades) on the target Linux host
* dt-oneagent-install-windows.yml - Installs Dynatrace OneAgent (or upgrades) on the target Windows host
* dt-api-application-config.yml - Creates a Dynatrace RUM Web Application using the Config API
* dt-api-management-zone.yml - Creates a Dynatrace Management Zone using the Config API
* dt-api-alerting-profile.yml - Creates a Dynatrace Alerting Profile using the Config API
* dt-api-dashboard-clone.yml - Creates a Dynatrace dashboard from an existing template using the Config API
* dt-onboarding-workflow-set-stats.yml - Helper Playbook that sets artifacts for a workflow utilizing each Playbook

The comments at the top of each Playbook contain the list of extra variables that are expected.

## OneAgent Install on Linux
By default, Ansible uses SSH to connect and manage Linux hosts\
By default, Ansible assumes you are using SSH keys to connect to remote machines. SSH keys are encouraged, but you can use password authentication if needed\
Control Nodes will need remote network access to managed Linux hosts on TCP port 22\
Authentication Options
* Username and password of target host for password authentication
* Ansible RSA key added to target host for key based authentication
* RSA key of target host for key based authentication

_User Account will need sudo root access to install the OneAgent_

**Python SSL Support**\
On the target systems, you need to ensure that python is compiled with SSL support.\
`python -c "import ssl; print(ssl.OPENSSL_VERSION)"`

## OneAgent Install on Windows
Ansible can manage Windows hosts using WinRM
* Windows Remote Management (WinRM) is the Microsoft implementation of WS-Management Protocol, a standard Simple Object Access Protocol (SOAP)-based, firewall-friendly protocol that allows hardware and operating systems, from different vendors, to interoperate.
* The WinRM Python module must be installed on the Ansible Control Node(s)
* WinRM must be set up on the target Windows hosts
https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html#winrm-setup
* Control Nodes will need remote network access to managed Windows hosts on TCP port 5986 (default)

