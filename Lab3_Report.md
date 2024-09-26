# Lab 3: Router Configuration (Creating Passwords, Configuring Interfaces)

## Objective
To configure a router by setting up passwords and interfaces to secure access and ensure connectivity between devices.

## Materials Required
- Packet Tracer software

## Theory
### Basics of Router Configuration
Router configuration involves setting up the device to handle network traffic efficiently. Key configuration tasks include setting IP addresses, configuring interfaces, and securing access to the router’s management features.

### Importance of Securing Router Access
Securing router access is essential to prevent unauthorized manipulation of the network. This includes:
- **Console Password**: Secures access through the console port.
- **Enable Password**: Protects privileged EXEC mode.
- **VTY Password**: Secures remote access via Telnet/SSH.

## Procedure
1. **Open Packet Tracer**:
   - Create a network topology consisting of one router and two computers.

2. **Access the Router's CLI**:
   - Click on the router and navigate to the **CLI** tab.

3. **Set Up Passwords**:
   - Enter the following commands to configure passwords:
     ```bash
     enable
     configure terminal
     # Set console password
     line con 0
     password your_console_password
     login
     exit
     
     # Set enable password
     enable secret your_enable_password
     
     # Set VTY password
     line vty 0 4
     password your_vty_password
     login
     exit
     ```

4. **Configure Router Interfaces**:
   - Assign IP addresses to the router interfaces that connect to each computer:
     ```bash
     interface gig0/0
     ip address 192.168.1.1 255.255.255.0
     no shutdown
     
     interface gig0/1
     ip address 192.168.2.1 255.255.255.0
     no shutdown
     ```

5. **Configure Computers**:
   - Set Computer 1’s IP address to `192.168.1.2` and Computer 2’s IP address to `192.168.2.2`.
   - Set their default gateways to the respective router IP addresses.

6. **Test Connectivity**:
   - Use the ping command from each computer:
     - From Computer 1, ping `192.168.1.1` and `192.168.2.2`.
     - From Computer 2, ping `192.168.2.1` and `192.168.1.2`.

## Observations
- **Configuration Steps**:
  - Passwords for console, enable, and VTY access were successfully set.
  - Router interfaces were configured with the appropriate IP addresses.

- **Test Results**:
  - Computer 1 successfully pinged its own interface and Computer 2.
  - Computer 2 successfully pinged its own interface and Computer 1.

## Conclusion
Securing and configuring routers is crucial for maintaining network integrity. The lab demonstrated the importance of password protection and proper interface configuration to enable secure and reliable communication between devices. These practices are foundational for effective network management.
