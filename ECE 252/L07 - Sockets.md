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
	- `````c
	  struct sockaddr_in {
	  sa_family sin_family; /* Address family */
	  in_port_t sin_port; /* Port Number */
	  struct in_addr sin_addr; /*IPv4 Address */
	  }
	  struct sockaddr_in addr;
	  addr.sin_family = AF_INET;
	  addr.sin_port = htons(2520);
	  addr.sin_addr.s_addr = htonl(INADDR_ANY);
	  `````
- IPv4 addresses take the format of ``XXX.XXX.XXX.XXX``, where each grouping of ``XXX`` is number between 0 and 255
- ``INADDR_ANY`` indicates to choose the address of the current computer within the ``htonl(address)`` argument
- Ports are like an apartment number
	- No two processes can use the same port
	- Ports with numbers below 1024 are reserved for system services
	- ``ssh`` uses port 22, and is a default known port that ``ssh`` uses
#### Look-Ups
- ``int getaddrinfo(*node, *service, struct addrinfo *hints, struct addrinfo **res)`` is used to get the hostname
	- ``node`` - hostname to connect to; can be IP address
	- ``service`` - gets the defined port for protocol; recommended to use explicit port numbers (i.e. 80 for HTTP)
	- ``hints`` - optional; restrict what kind of connection you want
	- ``res`` - pointer to pointer to the structure that will be updated once it's done
- To free info that has been allocated, use ``freeaddrinfo()``

### Client
- If client, connect to server with ``int connect (sockfd, struct sockaddr *addr, len)``
	- ``sockfd`` - socket file descriptor
	- 