/***********Networking Basics***********/

_______Learning Objectives______
OSI Model
-What it is
-How many layers it has
-How it is organized
What is a LAN
Typical usage
Typical geographical size
What is a WAN
Typical usage
Typical geographical size
What is the Internet
What is an IP address
What are the 2 types of IP address
What is localhost
What is a subnet
Why IPv6 was created
TCP/UDP
What are the 2 mainly used data transfer protocols for IP (transfer level on the OSI schema)
What is the main difference between TCP and UDP
What is a port
Memorize SSH, HTTP and HTTPS port numbers
What tool/protocol is often used to check if a device is connected to a network

1. Osi Model(Open Systems Interconnection model)
is a conceptual model that provides a common basis for the co-ordination of standards development for the purpose of systems interconnection.[is a conceptual framework for how applications communicate over a network]
Communications between a computing system are split into abstraction layers:
	a. Physical
	b. Data link
	c. Network
	d. Transport
	e. Session
	f. Presentation
	g. Application

Each layer in the osi model has its own well defined functions and the functions of each layer communicate and interact with the layers immediately.

a. Application layer
Provides network services to end users.
Services are protocals that work with data the client is using.
i.e http
Supply and recieve data to Presentation layer.
Application-layer functions typically include file sharing, message handling, and database access, through the most common protocols at the application layer, known as HTTP, FTP, SMB/CIFS, TFTP, and SMTP. 
When identifying communication partners, the application layer determines the identity and availability of communication partners for an application with data to transmit.

b. Presentation layer
It establishes data formatting and data translation into a format specified by the application layer during the encapsulation of outgoing messages while being passed down the protocol stack, and possibly reversed during the deencapsulation of incoming messages when being passed up the protocol stack.
Simply put, it converts data from one format to another.
It handles protocal conversion, data encryption, data decryption, data compression/decompression.


c. Session layer
Creates the setup, controls the connections and ends the teardown between two or more computers.
Common functions include:-
	- user logon
	- name lookup
	- user logoff
Session layer establishes, manages and terminates the connections between the local and remote application.
It also provides for full-duplex, half-duplex, or simplex operation, and establishes procedures for checkpointing, suspending, restarting, and terminating a session between two related streams of data, such as an audio and a video stream in a web-conferencing application.

d. Transport layer
Is responsible for transmission of data in network connections.
Co-ordinates how much data is sent, how fast or where it goes.
Examples of widely used protocals
TCP - Transmission Control Protocal
UDP - User Datagram Protocal
It provides the functional and procedural means of transferring variable-length data sequences from a source host to a destination host from one application to another across a network, while maintaining the quality-of-service functions.
Transport protocols may be connection-oriented or connectionless.
This may require breaking large protocal data into segments(small chunks) since the network imposes a max packet size (MTU) maximum transmission unit.
Segmentation is the process of breaking data into small chunks(segments).
The transport layer also controls the reliability of a given link between a source and destination host through flow control, error control, and acknowledgments of sequence and existence. Some protocols are state- and connection-oriented. This means that the transport layer can keep track of the segments and retransmit those that fail delivery through the acknowledgment hand-shake system. The transport layer will also provide the acknowledgement of the successful data transmission and sends the next data if no errors occurred.

e. Network layer
Handles the routing of the data.
Each frame of data is determined if the data has reached its destination.
It sends and receives data transmisions.
TCP/IP is the common known network layer.
It also manages the mapping of logical addresses and physical addresses.
The network layer provides the functional and procedural means of transferring packets from one node to another connected in "different networks".
A network is a medium to which many nodes can be connected, on which every node has an address and which permits nodes connected to it to transfer messages to other nodes connected to it by merely providing the content of a message and the address of the destination node and letting the network find the way to deliver the message to the destination node, possibly routing it through intermediate nodes.

f. Data link
The data link layer provides node-to-node data transfer—a link between two directly connected nodes.
It detects and possibly corrects errors that may occur in the physical layer. 
It defines the protocol to establish and terminate a connection between two physically connected devices. 
It also defines the protocol for flow control between them.
It is divided into two sub-layers:-
	a. MAC (Medium Access Control)- responsible for controlling how devices in a network gain access to a medium and permission to transmit data.
	b. LLC (Logical link Control):responsible for identifying and encapsulating network layer protocols, and controls error checking and frame synchronization.
The Point-to-Point Protocol (PPP) is a data link layer protocol that can operate over several different physical layers, such as synchronous and asynchronous serial lines.

g. Physical layer
The Physical Layer is responsible for the transmission and reception of unstructured raw data between a device, such as a network interface controller, Ethernet hub, or network switch, and a physical transmission medium.
It converts the digital bits into electrical, radio, or optical signals.	

ref:
	https://en.wikipedia.org/wiki/OSI_model

Types of Networks
Common types of area networks are:-
	- LAN (Local Area Network)
	- WAN (Wide Area Network)
	- WLAN (Wireless Local area network)
	- MAN (Metropolitan area network)
	- SAN
	- CAN
	- PAN
1. LAN
A LAN connects network devices over a relatively short distance.
In TCP/IP networking, a LAN is often, but not always, implemented as a single IP subnet.

2. WAN
A WAN spans a large physical distance.
A WAN is a geographically-dispersed collection of LANs. A network device called a router connects LANs to a WAN. In IP networking, the router maintains both a LAN address and a WAN address.

The Internet (or internet)[a] is a global system of interconnected computer networks that uses the Internet protocol suite (TCP/IP)[b] to communicate between networks and devices.

MAC Address
MAC (Medium access control) is a string of characters that identifies a device on a network.
It’s tied to a key connection device in your computer called the network interface card, or NIC.
The NIC is essentially a computer circuit card that makes it possible for your computer to connect to a network.
A NIC turns data into an electrical signal that can be transmitted over the network.
Every NIC has a hardware address that’s known as a MAC address. Whereas IP addresses are associated with a networking software called TCP/IP, MAC addresses are linked to the hardware of network adapters.

All devices on the same network subnet have different MAC addresses.
MAC addresses are very useful in diagnosing network issues such as problems with IP addresses.

Difference Between MAC Address and IP Address
- An IP address represents software and a MAC address represents hardware.
- The MAC address identifies specific devices within the same local network and the IP address identifies those devices outside of the local network.

IP Address
A public IP address is an IP address that can be accessed over the Internet.
Private IP address, on the other hand, is used to assign computers within your private space without letting them directly expose to the Internet.
