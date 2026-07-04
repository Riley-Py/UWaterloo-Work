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
- To just send a message without establishing a connection, use ``sendto(sockfd, msg, length, flags, sockaddr* to, fromlength)`` and ``recvfrom(sockfd, buffer, length, flags, sockaddr* from, fromlength)``
### cURL
- Don't use sockets with URLs; use network communication and transfer request library called *cURL*
- Only for client-side; not meant for server-side operations
- Servers have "endpoints" that clients connect via HTTP for client to get response
	- Usually use the *REST (Representational State Transfer)* principle
		- To communicate, use ``GET`` request (get resource)
- Uses the ``libcurl`` library in C
- Example and walkthrough of code: 
	- `````c
	  #include <stdio.h>
	  #include <curl/curl.h>
	  
	  int main (int argc, char** argv) 
	  `````