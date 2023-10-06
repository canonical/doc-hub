In this tutorial we will install MicroStack in the simplest way possible, by deploying an **OpenStack 2023.1** (Antelope) cloud.

The cloud will only allow access to its VMs from the local host. To enable access from any host on your network, follow the [Single-node guided](/t/35765) tutorial instead.

## Requirements

You will need a single machine whose requirements are:

- physical or virtual machine running Ubuntu 22.04 LTS
- a multi-core amd64 processor ideally with 4+ cores
- a minimum of 16 GiB of free memory
- Juju 3.2.x

[note type="caution"]
**Caution:** Any change in IP address of the local host will be detrimental to the deployment. A virtual host will generally have a more stable address.
[/note]

## Deploy the cloud

### Install the **openstack** snap

Begin by installing the **openstack** snap:

    sudo snap install openstack --channel 2023.1

### Prepare the machine

Sunbeam can generate a script to ensure that the machine has all of the required dependencies installed and is configured correctly for use in MicroStack - you can review this script using:

    sunbeam prepare-node-script

or the script can be directly executed in this way:

    sunbeam prepare-node-script | bash -x && newgrp snap_daemon

The script will ensure some software requirements are satisfied on the host. In particular, it will:

* install the `openssh-server` deb package if it is not found
* install the **juju** snap if it is not found
* configure passwordless sudo for all commands for the current user (`NOPASSWD:ALL`)

### Bootstrap the cloud

Deploy the OpenStack cloud using the `cluster bootstrap` command and accept software defaults:

    sunbeam cluster bootstrap --accept-defaults

### Configure the cloud and obtain credentials

Now configure the deployed cloud using the `configure` command. The `--accept-defaults` option will provide sensible default values:

    sunbeam configure --accept-defaults --openrc demo-openrc

The above command provides regular (non-admin) user credentials by saving them to file `demo-openrc`. Admin credentials can be obtained and stored (in file `admin-openrc`) in this way :

    sunbeam openrc > admin-openrc

These credential files contain standard OpenStack parameters that define the cloud and provide user access to the cloud.

## Launch a VM

Verify the cloud by launching a VM called 'test' based on the 'ubuntu' image (Ubuntu 22.04 LTS). The `launch` command is used:

    sunbeam launch ubuntu --name test

Sample output:

``` text
Launching an OpenStack instance ...
Access instance with `ssh -i /home/ubuntu/.config/openstack/sunbeam ubuntu@10.20.20.200`
```

Connect to the VM over SSH using the command provided in the above output. Note that the VM will not be ready instantaneously; waiting time is mostly determined by the cloud's available resources:

    ssh -i /home/ubuntu/.config/openstack/sunbeam ubuntu@10.20.20.200

## Related how-tos

Now that OpenStack is set up, be sure to check out the following how-to guides:

* [Accessing the OpenStack dashboard](/t/36232)
* [Using the OpenStack CLI](/t/36231)
