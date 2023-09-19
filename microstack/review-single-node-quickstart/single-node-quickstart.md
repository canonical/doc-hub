This tutorial shows how to install MicroStack in the simplest way possible. It will deploy an **OpenStack 2023.1** (Antelope) cloud.

The cloud will only allow access to its VMs from the local host. To enable access from any host on your network, follow the [Single-node guided](/t/35765) tutorial instead.

## Requirements

You will need a single machine whose requirements are:

- physical or virtual machine running Ubuntu 22.04 LTS
- a multi-core amd64 processor ideally with 4+ cores
- a minimum of 16 GiB of free memory

[note type="caution"]
**Caution:** Any change in IP address of the local host will be detrimental to the deployment. A virtual host will generally have a more stable address.
[/note]

## Deploy the cloud

### Install the openstack snap

Begin by installing the openstack snap:

    sudo snap install openstack --channel 2023.1

### Prepare the machine

Sunbeam can generate a script to ensure that the machine has all of the required dependencies installed and is configured correctly for use in MicroStack - you can review this script using:

    sunbeam prepare-node-script

or the script can be directly executed in this way:

    sunbeam prepare-node-script | bash -x && newgrp snap_daemon

The script will ensure some software requirements are satisfied on the host. In particular, it will:

* install `openssh-server` if it is not found
* configure passwordless sudo for all commands for the current user (`NOPASSWD:ALL`)

### Bootstrap the cloud

Deploy the OpenStack cloud using the `cluster bootstrap` command and accept software defaults:

    sunbeam cluster bootstrap --accept-defaults

### Configure the cloud and obtain credentials

Now configure the deployed cloud using the `configure` command:

    sunbeam configure --accept-defaults --openrc demo-openrc

The above command provides normal user credentials (file `demo-openrc`). Admin credentials can be obtained in this way (file `admin-openrc`):

    sunbeam openrc > admin-openrc

## Launch a VM

Verify the cloud by launching a VM called 'test' based on the 'ubuntu' image (Ubuntu 22.04 LTS). The `launch` command is used:

    sunbeam launch ubuntu --name test

Sample output:

``` text
Launching an OpenStack instance ...
Access instance with `ssh -i /home/ubuntu/.config/openstack/sunbeam ubuntu@10.20.20.200`
```

Connect to the VM over SSH using the provided command. Note that the VM will not be ready instantaneously; waiting time is mostly determined by the cloud's available resources.

## Related howtos

Now that OpenStack is set up, be sure to check out the following howto guides:

* [Accessing the OpenStack dashboard](/t/36232)
* [Using the OpenStack CLI](/t/36231)
