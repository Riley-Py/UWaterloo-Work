### Network Communication
- Another form of [[L06 - IPC|IPC]]
- Communicate over the network
	- Can be a method of communication if the two processes are on the same machine

### Sockets
- Describes how to communicate over network in standard way - establishes channel between two processes
- Two ways to communicate: *datagrams* and *connection streams*
	- *Datagrams* - just message delivery, like sending out a letter, but are unordered and are one-way
	- *Connection streams* - like making a telephone call; both need to be on the line to communicate
- Here's how to create a stream in UNIX - ``int socket (domain, type, protocol)``
	- ``domain`` - address format (either IPv4 or IPv6); defined as ``AF_INET`` for IPv4
	- ``type`` - kind of information going to be sending; ``SOCK_DGRAM`` for datagrams and ``SOCK_STREAM`` for bidirectional byte stream
	- ``protocol`` - how data is transported over the connection.  Default is TCP/IP
- To close a socket, you use ``close`` 

#### Language Conventions
- Communicating over the network requires both systems to be speaking the same language
- Data can be organized from smallest-largest byte (*big-endian*) or largest-smallest (*little-endian*)
	- Diagram of this: 
		- ![[Pasted image 20260629093514.png]]
- In ``arpa/inet.h`` header, it contains functions to allow the translation to occur for both host/network 
	- ``htonl(address_32)`` - translate 4 byte int for network
	- ``htons(address_16)`` - translate 2 byte int for network
	- ``ntohl(address_32)`` translate 4 byte int for host
	- ``ntohs(address_16)`` - translate 2 byte int for host

### Addresses
- For socket address, you use ``struct sockaddr_in`` structure
	- `````
	  ```
- IPv4 addresses take the format of ``XXX.XXX.XXX.XXX``, where each grouping of ``XXX`` is number between 0 and 255
- ``INADDR_ANY`` indicates to choose the address of the current computer within the ``htonl(address)`` argument
- 