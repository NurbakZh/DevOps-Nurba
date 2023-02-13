## Result of ansible-playbook playbooks/docker.yml --diff
___
```
The following NEW packages will be installed:
  containerd.io docker-ce docker-ce-cli docker-ce-rootless-extras
  docker-scan-plugin libltdl7 libslirp0 pigz slirp4netns
0 upgraded, 9 newly installed, 0 to remove and 29 not upgraded.
changed: [retakeVM]

TASK [nurba : Install docker-compose plugin.] *****************************************************************************************************************************
skipping: [retakeVM]

TASK [nurba : Install docker-compose-plugin (with downgrade option).] *****************************************************************************************************
skipping: [retakeVM]

TASK [nurba : Ensure /etc/docker/ directory exists.] **********************************************************************************************************************
skipping: [retakeVM]

TASK [nurba : Configure Docker daemon options.] ***************************************************************************************************************************
skipping: [retakeVM]

TASK [nurba : Ensure Docker is started and enabled at boot.] **************************************************************************************************************
ok: [retakeVM]

TASK [nurba : Ensure handlers are notified now to avoid firewall conflicts.] **********************************************************************************************

RUNNING HANDLER [nurba : restart docker] **********************************************************************************************************************************
changed: [retakeVM]

TASK [nurba : include_tasks] **********************************************************************************************************************************************
included: /Users/nurbakzh/Downloads/labs/DevOps-Nurba/ansible/roles/nurba/tasks/docker-compose.yml for retakeVM

TASK [nurba : Check current docker-compose version.] **********************************************************************************************************************
ok: [retakeVM]

TASK [nurba : set_fact] ***************************************************************************************************************************************************
ok: [retakeVM]

TASK [nurba : Delete existing docker-compose version if it's different.] **************************************************************************************************
ok: [retakeVM]

TASK [nurba : Install Docker Compose (if configured).] ********************************************************************************************************************
changed: [retakeVM]

TASK [nurba : Get docker group info using getent.] ************************************************************************************************************************
skipping: [retakeVM]

TASK [nurba : Check if there are any users to add to the docker group.] ***************************************************************************************************

TASK [nurba : include_tasks] **********************************************************************************************************************************************
skipping: [retakeVM]

PLAY RECAP *****************************************************************************************************************************************************************
retakeVM                   : ok=16   changed=6    unreachable=0    failed=0    skipped=12   rescued=0    ignored=0 
```

## Result of ansible-inventory -i inventory.yml --list
___
```
{
    "VM": {
        "hosts": [
            "retakeVM"
        ]
    },
    "_meta": {
        "hostvars": {
            "retakeVM": {
                "ansible_become": true,
                "ansible_host": "84.201.141.246",
                "ansible_ssh_private_key_file": "~/my_key",
                "ansible_user": "ubuntu"
            }
        }
    },
    "all": {
        "children": [
            "ungrouped",
            "VM"
        ]
    }
}
```