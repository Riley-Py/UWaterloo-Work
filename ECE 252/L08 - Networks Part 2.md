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
	  
	  int main (int argc, char** argv) {
	  
	  CURL *curl;
	  CURLcode res;
	  
	  curl_global_init(CURL_GLOBAL_DEFAULT);
	  curl = curl_easy_init();
	  
	  if (curl) {
	  curl_easy_setopt(curl, CURLOPT_URL, "https://example.com/");
	  res = curl_easy_perform(curl);
	  
	  if (res != CURLE_OK) {
		  fprintf(stderr, "curl easy perform() failed: %s\n", curl_easy_strerror(res));
	  }
	  curl_easy_cleanup(curl);
	  }
	  curl_global_cleanup();
	  return 0;
	  
	  }
	  `````
	  - ``CURL`` structure is "handle"; has to be initialized/cleaned up when finished
	  - ``CURLcode`` is also structure to find out how operations went
	  - ``curl_global_init()`` uses ``CURL_GLOBAL_DEFAULT``; if forgotten, ``curl_easy_init`` does it, but is dangerous
	  - Handle is initialized with ``curl_easy_init()``; connections are accessed through handle
		  - ``easy`` because there is a ``multi`` interface
	  - Set options for connection with URL
	  - Perform request with ``curl_easy_perform``; sends data over network and retrieves response; stores result in ``res``
	  - ``CURLE_OK`` is response code if everything went well
- Handle can be used multiple times; options have to be updated
- Cleanup handle with ``curl_easy_cleanup`` and then globally cleanup handle

### Setup of Callbacks
- *Callback* - tell the handle what function we would like like it to call when time comes
	- *Read callback* - uploading data to server (*POST*)
	- *Write callback* - receiving data from server (*GET*)
- Function for write callback is ``write_callback(ptr, size, nemb, userdata)``
	- ``ptr`` - points to data received
	- ``nmemb`` - size of data
	- ``size`` - always 1
	- ``userdata`` - pass data to the function
	- Returns number of bytes processed; if not equal to ``nemb``, then error
- Function for read callback is ``read_callback(buffer, size, nitems, inputdata)``
	- ``buffer`` - put data to send
	- ``size`` - size of each data element
	- ``nitems`` - number of items
	- Return value is number of bytes successfully put in buffer
- To register read and write callback
	1. Register the function
	2. Set the data
#ece252 
#L08 