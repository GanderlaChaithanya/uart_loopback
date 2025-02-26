# Uart_Loopback
## Introduction
The **UART (Universal Asynchronous Receiver-Transmitter) loopback** architecture is a self-test mechanism used to verify the functionality of a UART module within an FPGA. In this setup, the transmit (TX) and receive (RX) lines are internally connected, allowing data sent by the transmitter to be immediately received by the receiver. This eliminates the need for external peripherals during initial testing and debugging. 
**images**
### Architecture Components
The UART loopback architecture consists of the following key components:

### 1. FPGA (Field-Programmable Gate Array):
    
- The central processing unit that manages UART data transmission and reception.
 - Implements the loopback logic to internally connect TX to RX.
          
### 2. UART TX (Transmitter):
 - Converts parallel data (8-bit or other formats) into a serial bitstream.
 - Sends data out at a specified baud rate.
 - In loopback mode, this transmitted data is redirected to the RX input instead of being sent to an external device.
        
### 3. UART RX (Receiver):
  
- Captures the incoming serial bitstream and converts it back into parallel data.
- In loopback mode, it receives the exact data that was transmitted by TX.
### 4. Clock Source:
- Provides a precise timing reference for UART communication.
- Can be generated internally within the FPGA (e.g., an internal oscillator) or externally using a crystal oscillator.
  
### 5. Serial Interface (PC or USB-to-Serial Adapter):
- A connection between the FPGA and a host computer for testing.
- Terminal software such as PuTTY, Tera Term, or Arduino Serial Monitor can be used to send and receive data.
 ### 6. Loopback Path:
 - A direct internal connection between TX and RX inside the FPGA.
- Enables self-testing of the UART module without requiring external connections.
### Working Principle
1. Data Transmission: The FPGA’s UART TX transmits a data byte.
2. Loopback Connection: Instead of sending data externally, TX is internally wired to RX.
3. Data Reception: The UART RX captures the transmitted data and processes it as if it was received from an external source.
4. Verification: The received data is compared with the sent data to check for errors.
5. Repeat Process: The loopback mechanism continuously tests the UART module’s transmission and reception capabilities.
