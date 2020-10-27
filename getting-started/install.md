# Installation {#endpoint-download}

Following section describes how to install the Neuron software package on a Linux system device.

## Download

Neuron software package is available in EMQ website [https://www.emqx.io](https://www.emqx.io/).

| Package Name                                     | Architecture System   |
| ------------------------------------------------ | --------------------- |
| _neuron-x.y.z-linux-x86_64.tar.gz_               | x86 64-bit            |
| _neuron-x.y.z-linix-armv7l.tar.gz_               | ARM hardware floating |
| _neuron-x.y.z-linix-aarch64.tar.gz_              | ARM 64-bit            |

For the version number x.y.z, x is major version number which may change if the entire system structure enhancement, y is minor version number which may change if there will be some additional features. z is the patch number for bug fix in the Neuron software.

## Pre-requisites {#endpoint-pre-requisites}

The following Linux distros or devices have been tested for Neuron.

| Linux distros or devices                                                             | Neuron package required           |
| ------------------------------------------------------------------------------------ | --------------------------------- |
| **Debian package system for x86_64** <br>Ubuntu 20.xx<br>Ubuntu 18.xx Desktop<br>Ubuntu 16.xx Desktop (install openssl1.1)<br>Ubuntu 14.xx Desktop (install openssl1.1)  | neuron-x.y.z-linux-x86_64.tar.gz |
| **Redhat package system for x86_64** <br>Centos 8<br>Centos 7.x (install openssl1.1) | neuron-x.y.z-linux-x86_64.tar.gz  |
| **Raspberry Pi 2** <br>Pi 4b+<br>Pi 3b+<br>Pi 2b+ (install openssl1.1)               | neuron-x.y.z-linux-armv7l.tar.gz  |
| armv7l Ubuntu Linux System                                                           | neuron-x.y.z-linux-armv7l.tar.gz  |
| aarch64 Ubuntu Linux System                                                          | neuron-x.y.z-linux-aarch64.tar.gz |

Note: Some Linux distros require **openssl1.1** installation.
For Debian package, wget [http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.0g-2ubuntu4_amd64.deb](http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.0g-2ubuntu4_amd64.deb)
For Redhat package, [https://linuxscriptshub.com/update-openssl-1-1-0-centos-6-9-7-0](https://linuxscriptshub.com/update-openssl-1-1-0-centos-6-9-7-0/)

## New Installation {#endpoint-new-installation}

New Neuron software can be installed in a home directory of any user account. In case a user account is needed, we recommand &quot;neuron&quot; for installation.

1. Extracting the software package to any directory, (i.e. /home/neuron ):

   ```bash
   ~\$ tar -zxvf neuron-x.y.z-linux-x86_64.tar.gz
   ```

2. Run Neuron for the first time to buildup Neuron data directories _dat_:

   ```bash
   ~\$ {PATH}/neuron start
   ```

## Starting the Neuron System {#endpoint-starting}

To start Neuron system by the command:

```bash
~\$ {PATH}/neuron start
```

## Stopping the Neuron System {#endpoint-stopping}

To stop the running Neuron by the command:

```bash
~\$ {PATH}/neuron stop
```

## Checking the Neuron System {#endpoint-checking}

To checkup the status of Neuron:

```bash
~\$ {PATH}/neuron status
```

## Optional Switches {#endpoint-command}

Some more useful switches for &quot;neuron&quot; is available.

Usage: neuron [start|stop|status] [options]
| options:                        | description:                          |
| ------------------------------- | ------------------------------------- |
| -i or --instance `<instanceno>` |instance no `<0-9>`                    |
| -u or --uuid `<uuid>`           |universal unique id `<max 36 chars>`   |

## Running in Docker {#endpoint-docker}

To get the docker image from [https://hub.docker.com](https://hub.docker.com)

```bash
~\$ docker pull emqx/neuron:1.0.0
```

To start docker container

```bash
~\$ docker run -d --name neuron -p 7000:7000 emqx/neuron:1.0.0
```
