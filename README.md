# tobias_richter.netdata

[![Build Status](https://github.com/tobias-richter/ansible-netdata/workflows/CI/badge.svg)](https://github.com/tobias-richter/ansible-netdata/actions)

This role installs and managed netdata using [mrlesmithjr.netdata](https://galaxy.ansible.com/mrlesmithjr/netdata).

## Requirements

This role requires Ansible 2.7 or higher.

## Role Variables

See [defaults/main.yml](defaults/main.yml) for the documented role variables.

## Example Playbook

This playbook setups netdata and excludes loop, ram and dm disks from diskstats plugin.

    - hosts: users
	  roles:
	    - role: tobias_richter.netdata
          netdata_configs:
          - section: plugin:proc:/proc/diskstats
            option: "exclude disks"
            value: loop* ram* dm-* 
