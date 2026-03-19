# Task_Driven_Object_Detection_DVCON2026
This study introduces a combined software and hardware framework for task-centric object detection, built around the COCO-Tasks dataset.

# AXI4 Master Interface (GGNN Accelerator → VEGA)

This section provides details about the AXI4 Master interface signals used for communication between GGNN accelerator and VEGA. The table below maps Verilog signals to their corresponding VEGA AT1051 signals and describes their functionality.

## Signal Mapping Table

| **Verilog Signal** | **VEGA AT1051 Signal**     | **Description**                                      |
|---------------------|----------------------------|------------------------------------------------------|
| `awaddr`           | `AXI_SIDE_M0_AWADDR`      | Write address                                        |
| `awvalid`          | `AXI_SIDE_M0_AWVALID`     | Write address valid                                 |
| `awready`          | `AXI_SIDE_M0_AWREADY`     | Write address ready (input from VEGA)              |
| `wdata`            | `AXI_SIDE_M0_WDATA`       | Write data                                          |
| `wvalid`           | `AXI_SIDE_M0_WVALID`      | Write data valid                                   |
| `wready`           | `AXI_SIDE_M0_WREADY`      | Write data ready (input from VEGA)                |
| `bvalid`           | `AXI_SIDE_M0_BVALID`      | Write response valid (input from VEGA)            |
| `bready`           | `AXI_SIDE_M0_BREADY`      | Write response ready                               |
| `araddr`           | `AXI_SIDE_M0_ARADDR`      | Read address                                       |
| `arvalid`          | `AXI_SIDE_M0_ARVALID`     | Read address valid                                 |
| `arready`          | `AXI_SIDE_M0_ARREADY`     | Read address ready (input from VEGA)              |
| `rdata`            | `AXI_SIDE_M0_RDATA`       | Read data (input from VEGA)                       |
| `rvalid`           | `AXI_SIDE_M0_RVALID`      | Read data valid (input from VEGA)              |
| `rready`           | `AXI_SIDE_M0_RREADY`      | Read ready                       |


## Signal Descriptions

- **Write Address (`awaddr`)**: Specifies the target memory address for write operations.
- **Write Address Valid (`awvalid`)**: Indicates that the write address is valid and ready to be sent.
- **Write Address Ready (`awready`)**: A signal from VEGA indicating readiness to receive the write address.
- **Write Data (`wdata`)**: Contains the actual data to be written to the target memory address.
- **Write Data Valid (`wvalid`)**: Signals that the write data is valid and ready for transfer.
- **Write Data Ready (`wready`)**: A signal from VEGA indicating readiness to receive write data.
- **Write Response Valid (`bvalid`)**: Indicates that VEGA has processed the write operation and is sending a response.
- **Write Response Ready (`bready`)**: Signals readiness to receive a response for a completed write operation.
- **Read Address (`araddr`)**: Specifies the target memory address for read operations.
- **Read Address Valid (`arvalid`)**: Indicates that the read address is valid and ready to be sent.
- **Read Address Ready (`arready`)**: A signal from VEGA indicating readiness to receive the read address.
- **Read Data (`rdata`)**: Contains the actual data read from the target memory address.


---
# AXI4 Slave Interface (VEGA → GGNN Accelerator)

This section provides details about the AXI4 Slave interface signals used for communication between VEGA and GGNN accelerator. The table below maps Verilog signals to their corresponding VEGA AT1051 signals and describes their functionality.

## Signal Mapping Table

| **Verilog Signal** | **VEGA AT1051 Signal**     | **Description**                                      |
|---------------------|----------------------------|------------------------------------------------------|
| `awaddr`           | `AXI_SIDE_M1_AWADDR`      | Write address from VEGA                             |
| `awvalid`          | `AXI_SIDE_M1_AWVALID`     | Write address valid from VEGA                      |
| `awready`          | `AXI_SIDE_M1_AWREADY`     | Write address ready (output to VEGA)               |
| `wdata`            | `AXI_SIDE_M1_WDATA`       | Write data from VEGA                                |
| `wvalid`           | `AXI_SIDE_M1_WVALID`      | Write data valid from VEGA                         |
| `wready`           | `AXI_SIDE_M1_WREADY`      | Write data ready (output to VEGA)                  |
| `bvalid`           | `AXI_SIDE_M1_BVALID`      | Write response valid (output to VEGA)              |
| `bready`           | `AXI_SIDE_M1_BREADY`      | Write response ready from VEGA                     |
| `araddr`           | `AXI_SIDE_M1_ARADDR`      | Read address from VEGA                             |
| `arvalid`          | `AXI_SIDE_M1_ARVALID`     | Read address valid from VEGA                       |
| `arready`          | `AXI_SIDE_M1_ARREADY`     | Read address ready (output to VEGA)                |
| `rdata`            | `AXI_SIDE_M1_RDATA`       | Read data (output to VEGA)                         |
| `rvalid`           | `AXI_SIDE_M1_RVALID`      | Read data valid (output to VEGA)                   |
| `rready`           | `AXI_SIDE_M1_RREADY`      | Read ready from VEGA                               |

## Signal Descriptions

- **Write Address (`awaddr`)**: Specifies the target memory address for write operations, sent by VEGA.
- **Write Address Valid (`awvalid`)**: Indicates that the write address is valid and ready to be processed, sent by VEGA.
- **Write Address Ready (`awready`)**: A signal indicating readiness of GGNN accelerator to receive the write address.
- **Write Data (`wdata`)**: Contains the actual data to be written, sent by VEGA.
- **Write Data Valid (`wvalid`)**: Signals that the write data is valid and ready for transfer, sent by VEGA.
- **Write Data Ready (`wready`)**: A signal indicating readiness of GGNN accelerator to receive write data.
- **Write Response Valid (`bvalid`)**: Indicates that GGNN accelerator has processed the write operation and is sending a response.
- **Write Response Ready (`bready`)**: Signals readiness of VEGA to receive a response for a completed write operation.
- **Read Address (`araddr`)**: Specifies the target memory address for read operations, sent by VEGA.
- **Read Address Valid (`arvalid`)**: Indicates that the read address is valid and ready to be processed, sent by VEGA.
- **Read Address Ready (`arready`)**: A signal indicating readiness of GGNN accelerator to receive the read address.
- **Read Data (`rdata`)**: Contains the actual data read from the target memory address, sent by GGNN accelerator.
- **Read Data Valid (`rvalid`)**: Indicates that the read data is valid and ready for transfer, sent by GGNN accelerator.
- **Read Ready (`rready`)**: Signals readiness of VEGA to receive read data.

---
# Clock and Reset

This section describes the clock and reset signals used in the AXI4 interface.

## Signal Mapping Table

| **Verilog Signal** | **VEGA AT1051 Signal** | **Description**     |
|---------------------|------------------------|---------------------|
| `clk`              | `AXI_SIDE_CLK`        | AXI4 clock          |
| `rst`              | `AXI_SIDE_RST_N`      | Active-low reset    |

## Signal Descriptions

- **Clock (`clk`)**: The main clock signal for the AXI4 interface, provided by VEGA (`AXI_SIDE_CLK`).
- **Reset (`rst`)**: An active-low reset signal used to initialize or reset the AXI4 interface (`AXI_SIDE_RST_N`).

---
