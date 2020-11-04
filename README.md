# ami-bakery

## Overview

Permits the building of custom AMI images using Packer and Ansible.

## Notes

- Note that hard coded ARN references in `codebuild-projects.yml` need updated before use.
- The Packer provisioning script relies upon the AWS cloud-init process updating APT `sources.list` before continuing. If this step starts to timeout, review whether the AWS APT mirrors added after first boot still contain the string "ec2" and adjust accordingly.

## Files

* `buildspec.yml` - installs and configures Packer
* `ubuntu-bionic-patched_packer-template.json` - Packer config that invokes Ansible
* `ansible/playbook.yml` - includes hardening role and variables

## Ansible playbook

The playbook is stored within the `ansible` directory and is a bare bones implementation to be run with `ansible-local` on the server being configured.
Currently uses [DevSec Ansible OS hardening](https://github.com/dev-sec/ansible-os-hardening) installed via Galaxy.
# ami-bakery
# ami-bakery
