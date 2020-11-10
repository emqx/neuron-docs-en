# EMQ X Neuron Introduction

EMQ X Neuron is an industrial protocol gateway software running on various IoT edge gateway hardware. It supports one-stop access and analysis of dozens of industrial protocols, which is then converted into MQTT protocol to access the IIoT platform. Users can realize online gateway configuration management through the Web-based management console; Neuron has very low resource occupancy, and it supports X86, ARM, and MIPS three main CPU architectures.

- Support Modbus，OPCUA，IEC61850，IEC104 and BACnet protocols and equipment.
- Web control dashboard, user can use web browser to perform the visual configuration to realize data access across industrial equipment.
- Northbound MQTT data transmission is according to the user-specified configuration, the data is sent to specific MQTT broker server.
- Southbound communication monitors the data subject of the control device, and forwards related control commands to the device. Combined with the rule engine function provided by EMQ X Kuiper, it can quickly realize rule-based device control.
- Local data storage realize the storage and viewing of the original data of the equipment.

Neuron integrates with other EMQ products at the edge, which can easily achieve an end-to-end [cloud-edge collaborative IIoT solutions](https://www.emqx.io/cn/blog/emq-industrial-internet-cloud-edge-integrated-solution)。

**Reading related materials accordingly**

## Installation and Quick Guide

- [Installation](getting-started/install.md): Download and installation process documents under different operating systems.

- [Quick Guide](getting-started/quick_start.md): 3 minutes Neuron Docker tutorial, Neuron reads data from Modbus TCP simulator and displays the original data in the management console.

## Management console configuration

- Neuron provides a web-based management console interface, through which users can implement visual configuration in the browser.

## Script programming

- [Script](neuron-scripts/script-routines.md): is used to control the devices or perform the formula calculation.

## Driver list and instructions

- [Driver List](address-format/address-format.md): Neuron has a list of common drivers for field communication and its technical details.

