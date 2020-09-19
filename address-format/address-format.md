# Neuron Driver Address Format

## General {#endpoint-general}

This document describes the tag address formats for Neuron to setup with various kind of industrial protocol drivers. Each Neuron driver has its own address format that will be parsed in configuration process for machine or device communication.

## Allen-Bradley PLC2 (half duplex) {#endpoint-PLC2}

General Details

| Runtime module name | neuron_o_df1hp2 |
| ------------------- | --------------- |
| Driver name         | df1hp2          |
| Protocol            | DF1 half-duplex |
| Physical interface  | RS485           |
| Default settings    | 9600/8/N/1      |

# STN!DST!ADDR

**STN** is the slave station device number

**DST** is the destination node (CPU)

**ADDR** is the register address as following:

| Word |     | DDDDD | 0 ~ 65535 | Work Area (word) |
| ---- | --- | ----- | --------- | ---------------- |


Note: Because the 1771KG is directly connected to the CPU, the STN and DST should be set to the same number (address of 1771KG module).

Example: 16!16 (slave number 20 octal)

16!16!520 (word 1010 octal in slave number 20 octal)

Set 8 (10 octal) for 1771-KG and set 0 for 1785-KE and 1770-KF2 in KG mode

## Allen-Bradley PLC5 (half duplex) {#endpoint-PLC5}

General Details

| Runtime module name | neuron_o_df1ph5 |
| ------------------- | --------------- |
| Driver name         | df1ph5          |
| Protocol            | DF1 half-duplex |
| Physical interface  | RS485           |
| Default settings    | 9600/8/N/1      |

# STN!DST!ADDR

**STN** is the slave station device number (KE/KF2 module address)

**DST** is the destination node (CPU)

**ADDR** is the register address as following.

| Word |     | DDDDD | 0 ~ 65535 | Work Area (word) |
| ---- | --- | ----- | --------- | ---------------- |


Note: the KE or KF2 module inserts its address as the source, and this address will be the used data file number in the PLC5.

Example: 28!16 (KE/KF2 module number 34 octal and destination node=CPU number 20 octal). 28!16!10 means word 10 in file N28 in slave number 20 (octal).

Set 8 (10 octal) for 1771-KG and set 0 for 1785-KE and 1770-KF2 in KG mode

## Schneider Modbus RTU for TSX7 SCM {#endpoint-TSX7-SCM}

General Details

| Runtime module name | neuron_o_tsxmbr |
| ------------------- | --------------- |
| Driver name         | tsxmbr          |
| Protocol            | Modbus RTU      |
| Physical interface  | RS232           |
| Default settings    | 9600/8/N/1      |

# STN!ADDR

**STN** is the slave station number (CPU) (1 – 247)

**ADDR** is the register address as following.

| Word | W   | DDDDD | 0 ~ 32767 | Register (word) |
| ---- | --- | ----- | --------- | --------------- |


Example: **10!W100** means word 100 in slave station 10.

## Schneider Modbus TCP {#endpoint-TCP}

General Details

| Runtime module name | neuron_o_tsxmbt |
| ------------------- | --------------- |
| Driver name         | tsxmbt          |
| Protocol            | Modbus TCP      |
| Physical interface  | Ethernet        |
| Default settings    | Port: 502       |

# ADDR

**ADDR** is the register address as following:

| Word | W   | DDDDD | 0 ~ 32767 | Register |
| ---- | --- | ----- | --------- | -------- |


Example:**W4000** means word address 4000.

## Schneider Telemecanique UNI-TE {#endpoint-UNI-TE}

General Details

| Runtime module name | neuron_o_unite                                                                         |
| ------------------- | -------------------------------------------------------------------------------------- |
| Driver name         | unite                                                                                  |
| Protocol            | TSX SCM 2161 (Uni-Telway), directly on the built-in UNI-TE port on a V4 (or later) CPU |
| Physical interface  | RS232                                                                                  |
| Default settings    | 9600/8/N/1                                                                             |

# STN!ADDR

**STN** is the slave station number (Ad0 in CPU) (1 – 31)

**ADDR** is the register address as following:

| Word | W   | DDDDD | 0 ~ 32767 | Register (word) |
| ---- | --- | ----- | --------- | --------------- |


Example: **1!W100** means word 100 in slave number 1.

## ABB SattControl Comli {#endpoint-Comli}

General Details

| Runtime module name | neuron_o_comli |
| ------------------- | -------------- |
| Driver name         | comli          |
| Protocol            | comli          |
| Physical interface  | RS232          |
| Default settings    | 9600/8/N/1     |

# STN!ADDR

**STN** is the slave station number (CPU) (1 – 247)

**ADDR** is the register address as following

| Word | R   | DDDD | 0 ~ 3071 | Register (word) |
| ---- | --- | ---- | -------- | --------------- |


Example: **1!R100** means word 100 in slave number 1.

## Omron Single HostLink (Point to Point) {#endpoint-Single-HostLink}

General Details

| Runtime Instance   | neuron_o_omrhls           |
| ------------------ | ------------------------- |
| Driver Name        | omrhls                    |
| Protocol           | Host-Link sysmac c-series |
| Physical Interface | RS232                     |
| Default settings   | 9600/8/N/1                |

# ADDR

**ADDR** is the register address as following:

| Word | AR  | DDDD | 0 ~ 4095 | Auxiliary Relay        |
| ---- | --- | ---- | -------- | ---------------------- |
| Word | IR  | DDDD | 0 ~ 4095 | I/O and Internal Relay |
| Word | HR  | DDDD | 0 ~ 4095 | Hold Relay             |
| Word | LR  | DDDD | 0 ~ 4095 | Link Relay             |
| Word | TC  | DDDD | 0 ~ 255  | Timer                  |
| Word | DM  | DDDD | 0 ~ 9999 | Data Register          |

Example: **DM100** means word 100 in DM data memory area.

## Omron Multiple HostLink (MasterSlave) {#endpoint-HostLink}

General Details

| Runtime Instance   | neuron_o_omrhls           |
| ------------------ | ------------------------- |
| Driver Name        | omrhls                    |
| Protocol           | Host-Link sysmac c-series |
| Physical Interface | RS232                     |
| Default settings   | 9600/8/N/1                |

# STN!ADDR

**STN** is station number/module number (0 – 31)

**ADDR** is the register address as following:

| Word | AR  | DDDD | 0 ~ 4095 | Auxiliary Relay        |
| ---- | --- | ---- | -------- | ---------------------- |
| Word | IR  | DDDD | 0 ~ 4095 | I/O and Internal Relay |
| Word | HR  | DDDD | 0 ~ 4095 | Hold Relay             |
| Word | LR  | DDDD | 0 ~ 4095 | Link Relay             |
| Word | TC  | DDDD | 0 ~ 255  | Timer                  |
| Word | DM  | DDDD | 0 ~ 9999 | Data Register          |

Example: **10!DM100** means word 100 in data memory in slave 10.

## Siemens S5 3964R/RK512 {#endpoint-siemens-s5}

General Details

| Runtime Instance   | neuron_o_s539rk |
| ------------------ | --------------- |
| Driver Name        | s539rk          |
| Protocol           | 3964R/RK512     |
| Physical Interface | RS232           |
| Default settings   | 9600/8/N/1      |

# DBddd.DBWddddd

**ADDR** is the address as following

DB is the data block (0 – 999)

DBW(_ **word offset** _) is the data word in that data block

| Word | I           | DDDD       | 0 ~ 4095           | Input         |
| ---- | ----------- | ---------- | ------------------ | ------------- |
| Word | Q           | DDDD       | 0 ~ 4095           | Output        |
| Word | M           | DDDD       | 0 ~ 4095           | Marker Memory |
| Word | DB0~999.DBW | DDDDDDDDDD | 0 ~ 655350 ~ 65535 | Data Memory   |
| Word | T           | DDD        | 0 ~ 255            | Timer         |
| Word | C           | DDD        | 0 ~ 255            | Counter       |

Example: DB100 (data block 100)

**DB100.DBW20** means data word 20 in data block 100

## Siemens S7 3964R/RK512 {#endpoint-siemens-s7}

General Details

| Runtime module name | neuron_o_s739rk |
| ------------------- | --------------- |
| Driver name         | S739rk          |
| Protocol            | 3964R/RK512     |
| Physical interface  | RS232           |
| Default settings    | 9600/8/N/1      |

# DBddd.DBWddddd

**ADDR** is the address as following

DB is the data block (0 – 999)

DBW(_ **byte offset** _) is the data word in that data block

| Byte | IW          | DDDD       | 0 ~ 4095           | Input                                  |
| ---- | ----------- | ---------- | ------------------ | -------------------------------------- |
| Byte | QW          | DDDD       | 0 ~ 4095           | Output                                 |
| Byte | MW          | DDDD       | 0 ~ 4095           | Marker Memory                          |
| Byte | DB0~999.DBW | DDDDDDDDDD | 0 ~ 655350 ~ 65535 | Data Memory (must be in even byte no.) |
| Byte | T           | DDD        | 0 ~ 255            | Timer                                  |
| Byte | C           | DDD        | 0 ~ 255            | Counter                                |

Note: The real DBW should be used (eg. DBW0, DBW2 etc) and the driver will read the byte start from 0 and the byte start from 2. It reads a word from byte 0, byte 2 respectively.

Example: DB100 (data block 100)

**DB100.DBW20** means data word 20 in data block 100

## Siemens FETCH/WRITE {#endpoint-siemens-fetch}

General Details

| Runtime module name | neuron_o_siefw               |
| ------------------- | ---------------------------- |
| Driver name         | siefw                        |
| Protocol            | Siemens Fetch/Write Protocol |
| Physical Interface  | Ethernet                     |
| Default settings    | Port: 2200                   |

# DBddd.DBWddddd

**ADDR** is the address as following

DB is the data block (0 – 999)

DBW(_ **byte offset** _) is the data word (start) in that data block.

| Byte | IW          | DDDD       | 0 ~ 4095           | Input                                 |
| ---- | ----------- | ---------- | ------------------ | ------------------------------------- |
| Byte | QW          | DDDD       | 0 ~ 4095           | Output                                |
| Byte | MW          | DDDD       | 0 ~ 4095           | Marker Memory                         |
| Byte | DB0~999.DBW | DDDDDDDDDD | 0 ~ 655350 ~ 65535 | Data Memory (must be in even byte no) |
| Byte | T           | DDD        | 0 ~ 255            | Timer                                 |
| Byte | C           | DDD        | 0 ~ 255            | Counter                               |

Note: There is a limitation in the protocol. The DB can only be between 1-255 and the start address of a read or write table cannot go beyond DBW2047, however the end of a table can. But during the test, it was possible to start at address DBW32766.

Note: In the Simatic PLC you just define a TCP/IP connection for either FETCH passive (read only) or WRITE passive (write only), listening on a certain port. Currently there is no FETCH/WRITE passive setting, so two connections with different ports are required, one for read and one for write.

Example: **DB200.DBW20** means data word 20 in data block 200.

## Siemens Industrial Ethernet S7 ISOTCP {#endpoint-siemens-industrial}

General Details

| Runtime module name | neuron_o_s7pro           |
| ------------------- | ------------------------ |
| Driver name         | s7pro                    |
| Protocol            | S7 ISO TCP (S7 protocol) |
| Physical interface  | Ethernet                 |
| Default settings    | Port: 102                |

# DBddd.DBWddddd

**ADDR** is the address as following

Note: DB is the data block (0 – 999)

DBW(_ **byte offset** _) is the data word (start) in that data block.

| Byte | IW         | DDDD       | 0 ~ 4095           | Input                                  |
| ---- | ---------- | ---------- | ------------------ | -------------------------------------- |
| Byte | QW         | DDDD       | 0 ~ 4095           | Output                                 |
| Byte | MW         | DDDD       | 0 ~ 4095           | Marker Memory                          |
| Byte | DB0~999DBW | DDDDDDDDDD | 0 ~ 655350 ~ 65535 | Data Memory (must be in even byte no.) |
| Byte | T          | DDD        | 0 ~ 255            | Timer                                  |
| Byte | C          | DDD        | 0 ~ 255            | Counter                                |

Example: **DB200.DBW20** means data word 20 in data block 200.

S7P_SCRTSAP is the source TSAP for S7 protocol

S7P_DSTTSAP is the destination TSAP for S7 protocol

## Mitsubishi FX0S/FX0N/FX1S/FX1N/FX2 {#endpoint-mitsubishi-fx0s}

General Details

| Runtime Instance   | neuron_o_fxnpro |
| ------------------ | --------------- |
| Driver Name        | fxnpro          |
| Protocol           | RS command      |
| Physical Interface | RS232           |
| Default settings   | 9600/7/E/1      |

# ADDR

**ADDR** is the register address

| Bit   | X   | OOO  | 0 ~ 377     | Input Relay           |
| ----- | --- | ---- | ----------- | --------------------- |
| Bit   | Y   | OOO  | 0 ~ 377     | Output Relay          |
| Bit   | M   | DDDD | 0 ~ 7999    | Auxiliary Relay       |
| Bit   | T   | DDD  | 0 ~ 255     | Timer Relay           |
| Bit   | C   | DDD  | 0 ~ 255     | Counter Relay         |
| Bit   | SM  | DDDD | 8000 ~ 9999 | Special Aux. Relays   |
| Bit   | S   | DDDD | 0 ~ 4095    | States                |
| Word  | TN  | DDD  | 0 ~ 255     | Timer Memory          |
| Word  | CN  | DDD  | 0 ~ 199     | Counter Memory        |
| Word  | D   | DDDD | 0 ~ 7999    | Data Register         |
| DWord | CN2 | DDD  | 200 ~ 255   | Counter Memory        |
| Word  | SD  | DDDD | 8000 ~ 9999 | Special Data Register |

Example: **D100** means word 100 in D data memory area.

## Mitsubishi FX2N/FX3U/FX3G Series {#endpoint-mitsubishi-fx2n}

General Details

| Runtime Instance   | neuron_o_fx3u3g |
| ------------------ | --------------- |
| Driver Name        | fx3u3g          |
| Protocol           | RS command      |
| Physical Interface | RS232           |
| Default settings   | 9600/7/E/1      |

# ADDR

**ADDR** is the register address as following:

| Bit   | X   | OOO  | 0 ~ 764     | Input Relay           |
| ----- | --- | ---- | ----------- | --------------------- |
| Bit   | Y   | OOO  | 0 ~ 764     | Output Relay          |
| Bit   | M   | DDDD | 0 ~ 7999    | Auxiliary Relay       |
| Bit   | T   | DDD  | 0 ~ 511     | Timer Relay           |
| Bit   | C   | DDD  | 0 ~ 255     | Counter Relay         |
| Bit   | SM  | DDDD | 8000 ~ 9999 | Special Aux. Relays   |
| Bit   | S   | DDDD | 0 ~ 4095    | States                |
| Word  | TN  | DDD  | 0 ~ 511     | Timer Memory          |
| Word  | CN  | DDD  | 0 ~ 199     | Counter Memory        |
| Word  | D   | DDDD | 0 ~ 7999    | Data Register         |
| DWord | CN2 | DDD  | 200 ~ 255   | Counter Memory        |
| Word  | SD  | DDDD | 8000 ~ 9999 | Special Data Register |
| Word  | R   | DDDD | 0 ~ 32767   | Extended Register     |

Example: **D100** means word 100 in D data memory area.

## Mitsubishi Melsec E71 for Q Series {#endpoint-mitsubishi-melsec}

General Details

| Runtime module name | neuron_o_mele71 |
| ------------------- | --------------- |
| Driver name         | mele71          |
| Protocol            | MELSEC E71      |
| Physical Media      | Ethernet        |
| Default settings    | Port: 2000      |

# ADDR

**ADDR** is the register address as following:

| Bit  | X   | HHHH    | 0 ~ 1fff    | Input Relay             |
| ---- | --- | ------- | ----------- | ----------------------- |
| Bit  | Y   | HHHH    | 0 ~ 1fff    | Output Relay            |
| Bit  | M   | DDDDD   | 0 ~ 61439   | Internal Relay          |
| Bit  | L   | DDDDD   | 0 ~ 32767   | Latch Relay             |
| Bit  | F   | DDDDD   | 0 ~ 32767   | Annunciator             |
| Bit  | V   | DDDDD   | 0 ~ 32767   | Edge Relay              |
| Bit  | B   | HHHH    | 0 ~ efff    | Link Relay              |
| Bit  | TC  | DDDD    | 0 ~ 2047    | Timer Coil              |
| Bit  | SS  | DDDDD   | 0 ~ 25471   | Retentive Timer Contact |
| Bit  | SC  | DDDDD   | 0 ~ 25471   | Retentive Timer Coil    |
| Bit  | CS  | DDDDD   | 0 ~ 25471   | Counter Contact         |
| Bit  | CC  | DDDDD   | 0 ~ 25471   | Counter Coil            |
| Bit  | SB  | HHH     | 0 ~ 7ff     | Special Link Relay      |
| Bit  | DX  | HHHH    | 0 ~ 1fff    | Direct Input            |
| Bit  | DY  | HHHH    | 0 ~ 1fff    | Direct Output           |
| Bit  | TS  | DDDD    | 0 ~ 2047    | Timer Contact           |
| Word | W   | HHHH    | 0 ~ 2fff    | Link Register           |
| Word | TN  | DDDD    | 0 ~ 2047    | Timer Current Value     |
| Word | SN  | DDDD    | 0 ~ 2047    | Retentive Timer Current |
| Word | CN  | DDDD    | 0 ~ 1023    | Counter Value           |
| Word | SW  | HHH     | 0 ~ 7ff     | Special Link Register   |
| Word | Z   | DD      | 0 ~ 19      | Index Register          |
| Word | ZR  | HHHHH   | 0 ~ fe7a5   | File Register           |
| Word | D   | DDDDDDD | 0 ~ 4212735 | Data Register           |
| Word | SD  | DDDD    | 0 ~ 2047    |
|      |

Example: **D100** means word 100 in D data memory area.

## Modbus RTU {#endpoint-modbus-rtu}

General Details

| Runtime Instance | neuron_o_mbsrtu |
| ---------------- | --------------- |
| Driver Name      | mbsrtu          |
| Protocol         | Modbus RTU      |
| Physical Media   | RS485           |
| Default settings | 9600/8/N/1      |

# STN!ADDR

**STN** is slave number or device ID (0-247)

**ADDR** is the register address as following:

| Bit  | 01/05/15 | 000001 ~ 065536 | Discrete Output Coils           |
| ---- | -------- | --------------- | ------------------------------- |
| Bit  | 02       | 100001 ~ 165536 | Discrete Input Contacts         |
| Word | 04       | 300001 ~ 365536 | Analog Input Registers          |
| Word | 03/06/16 | 400001 ~ 465536 | Analog Output Holding Registers |

## Modbus TCP {#endpoint-modbus-tcp}

General Details

| Runtime Instance   | neuron_o_mbstcp |
| ------------------ | --------------- |
| Driver Name        | mbstcp          |
| Protocol           | Modbus TCP      |
| Physical Interface | Ethernet        |
| Default settings   | Port: 502       |

# STN!ADDR

**STN** is slave number or device ID (0-247)

**ADDR** is the register address as following:

| Bit  | 01/05/15 | 000001 ~ 065536 | Discrete Output Coils           |
| ---- | -------- | --------------- | ------------------------------- |
| Bit  | 02       | 100001 ~ 165536 | Discrete Input Contacts         |
| Word | 04       | 300001 ~ 365536 | Analog Input Registers          |
| Word | 03/06/16 | 400001 ~ 465536 | Analog Output Holding Registers |

Example:**2!404001** means word address 4000 with in slave number 2.

## Modbus RTU over TCP {#endpoint-modbus-rtu-tcp}

General Details

| Runtime Instance   | neuron_o_mbsrot     |
| ------------------ | ------------------- |
| Driver Name        | mbsrot              |
| Protocol           | Modbus RTU over TCP |
| Physical Interface | Ethernet            |
| Default settings   | Port: 502           |

# STN!ADDR

**STN** is slave number or device ID (0-247)

**ADDR** is the register address as following:

| Bit  | 01/05/15 | 000001 ~ 065536 | Discrete Output Coils           |
| ---- | -------- | --------------- | ------------------------------- |
| Bit  | 02       | 100001 ~ 165536 | Discrete Input Contacts         |
| Word | 04       | 300001 ~ 365536 | Analog Input Registers          |
| Word | 03/06/16 | 400001 ~ 465536 | Analog Output Holding Registers |

Example:**2!404001** means word address 4000 with in slave number 2.

## IEC 61850 {#endpoint-iec-61850}

General Details

| Runtime Instance   | neuron_o_i61850 |
| ------------------ | --------------- |
| Driver Name        | i61850          |
| Protocol           | IEC 61850       |
| Physical Interface | Ethernet        |
| Default settings   | Port: 102       |

# FC!ADDR

**FC** is functional constraints value as following:

| 0   | IEC61850_FC_ST | Status information                  |
| --- | -------------- | ----------------------------------- |
| 1   | IEC61850_FC_MX | Measurands - analog values          |
| 2   | IEC61850_FC_SP | Setpoint                            |
| 3   | IEC61850_FC_SV | Substitution                        |
| 4   | IEC61850_FC_CF | Configuration                       |
| 5   | IEC61850_FC_DC | Description                         |
| 6   | IEC61850_FC_SG | Setting group                       |
| 7   | IEC61850_FC_SE | Setting group editable              |
| 8   | IEC61850_FC_SR | Service response / Service tracking |
| 9   | IEC61850_FC_OR | Operate received                    |
| 10  | IEC61850_FC_BL | Blocking                            |
| 11  | IEC61850_FC_EX | Extended definition                 |
| 12  | IEC61850_FC_CO | Control                             |
| 13  | IEC61850_FC_US | Unicast SV                          |
| 14  | IEC61850_FC_MS | Multicast SV                        |
| 15  | IEC61850_FC_RP | Unbuffered report                   |
| 16  | IEC61850_FC_BR | Buffered report                     |
| 17  | IEC61850_FC_LG | Log control blocks                  |

**ADDR** is the object reference address string

The IEC61850 data hierarchical model are usually as following:

Physical Device (IED)

Logical Device (LD)

Logical Node (LN)

Object Data (DO)

Object Attribute (DA)

Example:**1!testmodelSENSORS/TTMP1.TmpSv.instMag.f**

means the functional constraint of this tag is 1 (IEC61850_FC_MX –analog measurands). The object reference address string are (IED) – testmodel, (LD) – SENSORS, (LN) – TTMP1, (DO) – TmpSv, (DA) – instMag.f for floating value.

## OPC UA {#endpoint-opc-ua}

General Details

| Runtime Instance   | neuron_o_opcua |
| ------------------ | -------------- |
| Driver Name        | opcua          |
| Protocol           | OPC UA         |
| Physical Interface | Ethernet       |
| Default settings   | Port: 4840     |

# IX!NODEID

**IX** is the namespace index. (1-32767)

**NODEID** is the node ID. (any string exclude &#39;!&#39;)

Example: 2!Device1.Module1.Tag1 represents namespace index is 2 and node ID is Device1.Module1.Tag1

Please refer to OPC UA standard for the explanation of namespace index and node id.
