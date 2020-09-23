# Installation {#endpoint-download}

Following section describes how to install the Neuron software package on a x86 or ARM Linux device.

## Download

Neuron software package can be download from EMQ website [https://www.emqx.io](https://www.emqx.io/). For docker image, please download from docker hub website [https://hub.docker.com/r/emq/neuron](https://hub.docker.com/r/emq/neuron).

Neuron supports following Linux system:

For x86 64-bit system,<br>Download file: _neuron-0.5-x86_64.tar.gz_

For ARM hardware floating support system,<br>Download file: _neuron-0.5-armhf.tar.gz_

For ARM 64-bit system,<br>Download file: _neuron-0.5-arm64.tar.gz_

For the number 0.5, 0 is major version number which may change if the entire system structure enhancement, 5 is minor version number which may change if there will be some additional features or there are some bug fixed patches for the Neuron software.

Next token specifies the platform dependent for installation. For example, x86_64 means x86 64bit platform, arm64 means ARM 64bit platform, etc.

## Pre-requisites {#endpoint-pre-requisites}

The following Linux distros or devices have been tested for Neuron.

| Linux distros or devices                                                  | Neuron package required  |
| ------------------------------------------------------------------------- | ------------------------ |
| Debian package system for x86<br>Debian 9.x<br>Ubuntu 16.xx Desktop       | neuron-1.4-x86_64.tar.gz |
| Ubuntu 18.xx Desktop<br>Linuxmint 18                                      | neuron-1.4-x86_64.tar.gz |
| Redhat package system for x86<br>Fedora 30 Workstation<br>Centos 7.x-1810 | neuron-1.4-x86_64.tar.gz |
| Raspberry Pi 2                                                            | neuron-1.4-armhf.tar.gz  |
| Raspberry Pi 3                                                            | neuron-1.4-arm64.tar.gz  |
| Raspberry Pi 4                                                            | Neuron-1.4-arm64.tar.gz  |

## New Installation {#endpoint-new-installation}

This section describes how to install the Neuron software for the first time on Linux system. New Neuron software **MUST** be installed in a home directory of any user account. We recommend &quot;neuron&quot; account for installation.

Note: For the new installation, system user password might be required for creating user account.

1. Create a new Linux account &quot;neuron&quot; in your Linux distribution which will be used for Neuron software package installation. Or run following command to create a user account.

   ```bash
   ~\$ sudo useradd neuron -m -s /bin/bash
   ```

2. Exit and Login as &quot;neuron&quot; user to Linux prompt ~\$.

3. Download Neuron software package from EMQ website.

4. Extracting the software package to **\$HOME** directory, (i.e. /home/neuron ) enter the command:

   ```bash
   ~\$ tar -zxvf neuron-0.5-x86_64.tar.gz
   ```

5. Run Neuron first time to build data directories ~/dat. enter the command:

   ```bash
   ~\$ neuronsrt
   ```

6. Stop Neuron running, enter the command:

   ```bash
   ~\$ neuronsrt -s
   ```

## Setting the Shell Path {#endpoint-setting}

This section describes how to setup shell execution path for Neuron software. Different Linux distribution has its own way. Please refer to your Linux manual. For Ubuntu, the .bash_profile will be modified as follow:

```bash
# Neuron System environment

PATH=$PATH:$HOME/bin:.

NEURONPATH=\$HOME

export NEURONPATH

NEURONDATPATH=\$NEURONPATH/dat

export NEURONDATPATH
```

Notes: Both $NEURONPATH and $NEURONDATPATH are important variables for running Neuron in shell.

## Starting the System {#endpoint-starting}

This section describes how to start the Neuron.

1. login as &quot;neuron&quot;

2. The Neuron can be started by

```bash
~\$ neuronsrt
```

## Stopping the System {#endpoint-stopping}

This section describes how to stop the Neuron.

1. login as &quot;neuron&quot;

2. The Neuron will stops by entering the command

```bash
~\$ neuronsrt -s
```

## Command Switches {#endpoint-command}

This section describes the available switches for &quot;neuronsrt&quot; command.

| Switch | Description                     |
| ------ | ------------------------------- |
| -h     | print help.                     |
| -p     | print running status.           |
| -r     | restart only                    |
| -n     | restart with new configuration. |
| -s     | stop running                    |
| -f     | fix (dat) data directories.     |
