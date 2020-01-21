## Summary:
This repo is a collection of Ansible playbook yaml files designed for automating the onboarding of applications into Dynatrace.  These playbooks were written and tested on Red Hat Ansible Tower, but should work with other platforms such as vanilla Ansible and AWX.

## Playbooks:
* dt-oneagent-install-linux.yml - Installs Dynatrace OneAgent (or upgrades) on the target Linux host
* dt-oneagent-install-windows.yml - Installs Dynatrace OneAgent (or upgrades) on the target Windows host
* dt-api-application-config.yml - Creates a Dynatrace RUM Web Application using the Config API
* dt-api-management-zone.yml - Creates a Dynatrace Management Zone using the Config API
* dt-api-alerting-profile.yml - Creates a Dynatrace Alerting Profile using the Config API
* dt-api-dashboard-clone.yml - Creates a Dynatrace dashboard from an existing template using the Config API
* dt-onboarding-workflow-set-stats.yml - Helper Playbook that sets artifacts for a workflow utilizing each Playbook

The comments at the top of each Playbook contain the list of extra variables that are expected.
