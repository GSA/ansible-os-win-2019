Windows Server 2019 GSA Benchmarks
==================================
Configure Windows 2019 machine to be GSA compliant. Level 1 and 2 findings will be corrected by default. It's based on [Windows Server 2019 GSA Benchmarks](https://docs.google.com/spreadsheets/d/1F6ZH8CPMkKYqO8q4VSddl2kEdZnpOjYwR5_UnVvHHu4).


Role Variables
--------------
All the security configuration as per the GSA benchmark requirements are deployed by default. However, the users can control through the tags.

##### Following security configurations are hardened by this role:
* Access, Authentication and Authorization Configurations
* Windows Firewall Settings
* Audit Policy Settings
* Users configurations

### Dependencies
Ansible >= 2.7

### Example Playbook

```
---
- name: Harden Server
  hosts: all
  become: yes

  roles:
    - ansible-os-win2019
```

### How to test locally

```
ansible-playbook playbook.yml --connection=local
```
### CircleCI Intergration

This repository has been updated to optionally utilize Continuous Intergration with CircleCI and tests the ansbile tasks.  A low number of tasks are incompatiable when ran against a container vs a vm or bare-metal and have ignore_errors turned on.

##### Using CircleCI:
* Fork this repository or create a branch
* Sign up for an account and follow the getting started guide at https://circleci.com/docs/2.0/first-steps/#section=getting-started
* Add the repository to your projects and click start building. https://circleci.com/docs/2.0/project-build/#section=getting-started
* New Commits will trigger the CircleCI build and run the playbook.yml and the result will pass or fail.

### License

BSD.

