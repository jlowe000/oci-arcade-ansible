# oci-arcade-ansible
The purpose of this repository is to support more of the automation required to deploy oci-arcade.

There are two other repositories that this relates to:
- oci-arcade [https://github.com/jlowe000/oci-arcade] - the application itself
- oci-arcade [https://github.com/jlowe000/oci-arcade-tf] - the Terraform HCL scripts (that are capable of these TF scripts running in Oracle Cloud Infrastructure as part of the Oracle Resource Manager - Oracle-managed Terraform as a Service)

The contents here achieved the outcome:
- Using Ansible and the OCI Ansible Collection [https://oci-ansible-collection.readthedocs.io/en/latest/] to setup and teardown the OCI Arcade

At the moment:
- vars.yaml.template - specific variables that can be defined for the setup and teardown. needs to be copied as vars.yaml
- setup.yaml - to setup the OCI Arcade
- teardown.yaml - to teardown the OCI Arcade

Notes:
- Most of the provisioning is down through the Terraform scripts BUT: there minimal setup here required before the provisions starts.
- The OCI arcade is architected for the Always Free Tier.
- Oracle Resource Manager downloads the OCI Arcade Terraform scripts from github.com directly hence needing a github personal access token

Pre-Requisites:
- Ansible installed
- Ansible OCI Collection installed
- OCI tenancy - You can start here https://www.oracle.com/au/cloud/free/
- OCI SDK installed and configured to the tenancy
- Admin privileges to the tenancy
- OCI Arcade needs 1 x VCN, 2 x VM Compute, 1 Autonomous Database
- github Personal Access Token
