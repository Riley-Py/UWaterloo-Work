### Send/Receive Data
- Client/server can send/receive data
- For sending data in C, the function is ``send (sockfd, msg, length, flags)``
	- ``sockfd`` - socket file descriptor
		- Either ``socket()`` (client) or ``accept()`` (server)
	- ``msg`` - data being sent
	- ``length`` - specifies length of data being sent
	- ``flags`` - use 0
	- Returns number of bytes sent
- Should track number of bytes sent and keeping updating until number of bytes is equal to total amount of bytes
- For receiving data in C, the function is ``recv(sockfd, buffer, length, flags)``
	- ``sockfd`` - socket file descriptor
	- ``buffer`` - destination for the data being received
	- ``length`` - maximum size of buffer
	- ``flags`` - use 0
	- Return number of bytes written to buffer
- Can use ``struct`` to send more data, but it requires it to be the exact same for both client and server - solution below
	- *Serialization* - converting data to byte-representation so that it can be sent, then reconstructed via deserialization
		- No need for particular data format
		- Different systems can interact with one another
- After sending data, call the ``close()`` function

### Datagrams
- To just send a message without establishing a connection, use ``sendto(sockfd, msg, length, flags, sockadd)