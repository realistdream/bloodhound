# bloodhound

README 

*Overview*

bloodhound.py is a Python script designed to perform ARP (Address Resolution Protocol) scans on a specified IP range within a network. This tool identifies active devices, retrieves their IP and MAC addresses, and, if possible, determines the manufacturers of the hardware through vendor lookup.

*Prerequisites*

- Python 3.x

*Dependencies*

- scapy
- argparse
- re 
- prettytable
- mac_vendor_lookup

You can install the required modules using pip:

 > bash pip install scapy argparse prettytable mac-vendor-lookup

*Usage*

 > bash python DEVICEFINDER01.py <target_ip>

-- <target_ip>: The target IP range or individual IP address for scanning. The range should be specified in CIDR notation (e.g., 192.168.1.1/24).

*Description of Functionality*

ARP Scanning:

- The core function arp_scan(target_ip) constructs and sends ARP requests to the provided IP range to detect active devices. It combines ARP and Ethernet packets for broadcasting across the network and collects responses.

Output:

The script outputs a PrettyTable with the following columns:

IP: The IP address of the responding device.
MAC: The MAC address of the responding device.
Vendor: The device vendor/manufacturer. If the vendor is unknown, it defaults to "Unknown".

Example

To scan an entire subnet:

 > bash python bloodhound.py 192.168.1.1/24

The result will be a table displaying each responding device's IP, MAC address, and vendor name, if identified.

*Error Handling*
Vendor Lookup Failure: If the vendor lookup fails for a device, the script records "Unknown" for its vendor.


License
This project is licensed under the MIT License - see the LICENSE.md file for details.
