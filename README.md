# vcd-cli

[![License](https://img.shields.io/pypi/l/vcd-cli.svg)](https://pypi.python.org/pypi/vcd-cli) [![Stable Version](https://img.shields.io/pypi/v/vcd-cli.svg)](https://pypi.python.org/pypi/vcd-cli)

`vcd-cli` is the Command Line Interface for VMware vCloud Director.

## Forked from

https://github.com/vmware-archive/vcd-cli

## Installation

1. (Optional) Create a python virtual environment to install this cli into.

2. Execute the following command:

```shell
$ pip install git+https://github.com/juan-tec/vcd-cli.git
```

3. Verify the installation by running:

```shell
$ vcd
```

Depending on your operating system and distribution you may need
additional packages to install successfully.   See [install.md](docs/install.md)
for full details.

## Added features
### Reset system uuid
For the command `vcd vapp add-vm` used to the deploy a VM in a vApp based on a catalog vApp template, a new flag was added to allow the user avoid the new VM keep the same system/bios uuid of the VM from the vApp template.

This flag is now listed in the description of the command:

<pre>
Usage: vcd vapp add-vm [OPTIONS] <target-vapp> <source-vapp> <source-vm>

Options:
  -c, --catalog name             Name of the catalog if the source vApp is a
                                 template
  -t, --target-vm name           Rename the target VM with this name
  -o, --hostname hostname        Customize VM and set hostname in the guest OS
  -n, --network name             vApp network to connect to
  -i, --ip-allocation-mode mode  IP allocation mode
  -s, --storage-profile name     Name of the storage profile for the VM
  --password-auto                Autogenerate administrator password
  <b>--reset-system-uuid            Set a new system UUID for the VM</b>
  --accept-all-eulas             Accept all EULAs
  -h, --help                     Show this message and exit.
</pre>
