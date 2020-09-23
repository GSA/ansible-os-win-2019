Windows Server 2019 GSA Benchmark   [![documentation](https://img.shields.io/badge/documentation-ansible-blue.svg)](https://docs.ansible.com/ansible/latest/user_guide/windows.html) [![CircleCI](https://circleci.com/gh/GSA/ansible-os-win-2019.svg?style=shield)](https://circleci.com/gh/GSA/ansible-os-win-2019)
=================================

This Ansible content will configure a Windows Server 2019 machine to be GSA compliant.

This role **will make changes to the system** that could impact its performance and/or availability.

For configuration compliance auditing, use a tool such as [Nessus](https://www.tenable.com/products/nessus) or [CIS-CAT](https://learn.cisecurity.org/cis-cat-lite)

This hardening content is based on the GSA Microsoft Windows Server 2019 Security Benchmark v1.0 and the [CIS Microsoft Windows Server 2019 Benchmark v1.1.0 ](https://www.cisecurity.org/cis-benchmarks/).

Important Information
---------------------

Before executing, you should carefully review the playbook tasks to make sure your systems will not be negatively impacted.

Please thoroughly review to ensure your organizational requirements are met.

##### The current default configuration will:
* Configure all Windows Firewall controls except for "Ensure 'Windows Firewall - Public - Inbound connections' is set to 'Block (default)'"
* Configure Windows Update controls

##### The configuration will NOT:
* Set the 'Minimum password length' to 16 or more characters
* Configure 'Deny access to this computer from the network' to include Local Accounts
* Configure 'Deny log on through Remote Desktop Services' to include Local Accounts

Example Playbook
----------------
```
---
- name: Harden Win2019 Server
  hosts: all
  tasks:
       - include_role:
           name: ansible-os-win-2019
       - import_tasks:
```

 Public domain
 -------------

 This project is in the worldwide [public domain](LICENSE.md). As stated in [CONTRIBUTING](CONTRIBUTING.md):

 > This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
 >
 > All contributions to this project will be released under the CC0 dedication. By submitting a pull request, you are agreeing to comply with this waiver of copyright interest.
