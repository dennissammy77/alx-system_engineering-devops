_______Networking basics #1_____

Learning Objectives

What is localhost/127.0.0.1
What is 0.0.0.0
What is /etc/hosts
How to display your machine’s active network interfaces

/****Localhost****/

localhost is a hostname that refers to the current device used to access it. 
It is used to access the network services that are running on the host via the loopback network interface. 
Using the loopback interface bypasses any local network interface hardware.
The local loopback mechanism may be used to run a network service on a host without requiring a physical network interface, or without making the service accessible from the networks the computer may be connected to. 
For example, a locally installed website may be accessed from a Web browser by the URL http://localhost to display its home page.

IPv4 network standards reserve the entire address block 127.0.0.0/8 (more than 16 million addresses) for loopback purposes.[2] That means any packet sent to any of those addresses is looped back.
The address 127.0.0.1 is the standard address for IPv4 loopback traffic; the rest are not supported by all operating systems. 
However, they can be used to set up multiple server applications on the host, all listening on the same port number.

What is 0.0.0.0?
It tells a server to "listen" for and accept connections from any IP address. On PCs and client devices. A 0.0. 0.0 address indicates the client isn't connected to a TCP/IP network, and a device may give itself a 0.0. 0.0 address when it is offline.

What is the hosts file?
The computer file hosts is an operating system file that maps hostnames to IP addresses. 
It is a plain text file. Originally a file named HOSTS.
A hosts file which is used by operating systems to map a connection between an IP address and domain names before going to domain name servers.

Netcat
Netcat or nc is a networking utility for debugging and investigating the network.
This utility can be used for creating TCP/UDP connections and investigating them. 
The biggest use of this utility is in the scripts where we need to deal with TCP/UDP sockets.

1. Netcat in a Server-Client Architecture
The netcat utility can be run in the server mode on a specified port listening for incoming connections.
	nc -l 2389
it can be used in client mode trying to connect on the port(2389) just opened
	nc localhost 2389
netcat utility can be used in the client server socket communication.

2. Use Netcat to Transfer Files
The netcat utility can also be used to transfer files. At the client side, suppose we have a file named ‘testfile’ containing :

$ cat testfile
hello test

and at the server side we have an empty file ‘test’
Now, we run the server as :

$ nc -l 2389 > test
and run the client as :

cat testfile | nc localhost 2389

3. Netcat Supports Timeouts
There are cases when we do not want a connection to remain open forever. In that case, through ‘-w’ switch we can specify the timeout in a connection. So after the seconds specified along with -w flag, the connection between the client and server is terminated.
Server :

nc -l 2389
Client :

$ nc -w 10 localhost 2389
The connection above would be terminated after 10 seconds.

NOTE : Do not use the -w flag with -l flag at the server side as in that case -w flag causes no effect and hence the connection remains open forever.

4. Netcat Supports IPV6 Connectivity
The flag -4 or -6 specifies that netcat utility should use which type of addresses.
-4 forces nc to use IPV4 address while -6 forces nc to use IPV6 address

5. Disable Reading from STDIN in Netcat
This functionality can be achieved by using the flag -d. In the following example, we used this flag at the client side.

Server :

$ nc -l 2389
Client :

$ nc -d localhost 2389
Hi
The text ‘Hi’ will not be sent to the server end as using -d option the read from stdin has been disabled.

6. Force Netcat Server to Stay Up
If the netcat client is connected to the server and then after sometime the client is disconnected then normally netcat server also terminates.

Server :

$ nc -l 2389
Client :

$ nc localhost 2389
^C
Server :

$ nc -l 2389
$
So, in the above example we see that as soon as the client got disconnected the server was also terminated.

This behavior can be controlled by using the -k flag at the server side to force the server to stay up even after the client has disconnected.
Server :

$ nc -k -l 2389
Client :

$ nc localhost 2389
^C
Server :

$ nc -k -l 2389
So we see that by using the -k option the server remains up even if the client got disconnected.

7. Configure Netcat Client to Stay Up after EOF
Netcat client can be configured to stay up after EOF is received. 
In a normal scenario, if the nc client receives an EOF character then it terminates immediately but this behavior can also be controlled if the -q flag is used. 
This flag expects a number which depicts number of seconds to wait before client terminates (after receiving EOF)

Client should be started like :

nc  -q 5  localhost 2389
Now if the client ever receives an EOF then it will wait for 5 seconds before terminating.

8. Use Netcat with UDP Protocol
By default all the sockets that nc utility creates are TCP protocols but this utility also works with UDP protocol.
To enable UDP protocol the -u flag is used.

Server :

$ nc -4 -u -l 2389
Client :

$ nc -4 -u localhost 2389
Now, both the server and client are configured to use UDP protocol. 
This can be confirmed by the following netstat command. So we see that this connection is now using the UDP protocol.
