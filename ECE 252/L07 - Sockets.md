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