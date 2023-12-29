# Ansible Fortigate Cloudinit

## Description
Fortigate provides the ability to deploy both the configuration and the license for the Fortigate VM during its boot phase. This functionality enables the firewall to be fully operational immediately after booting, removing the necessity for initial setup of the interface and routing. Additionally, Cloudinit is compatible with all recognized CLI configurations. With this Ansible playbook, it's possible to download a license from the Fortinet Portal, render a CLI template using Jinja2, and create an ISO file using Xorriso, which can then be attached as a boot ISO to the VM.

```
cloud-init
└── openstack
├── content
│   └── 0000 – License file
└── latest
└── user_data – Configuration file
```

## Command to run locally

```
ansible-playbook main.yml --extra-vars="@extravars.json"
```

## Important Note
If you want to use the playbook locally, it's important to provide the FortiCloud API access credentials and have xorriso installed locally. If you are using it in conjunction with AWX Tower, make sure that your AWX Execution Environment has xorriso installed. In AWX, credentials can be provided in two ways: they can be either directly hard-coded in the inventory YML file for simplicity or, for added security, provided via the AWX Credentials Vault.

