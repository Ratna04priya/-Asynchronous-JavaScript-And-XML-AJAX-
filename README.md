# -Asynchronous-JavaScript-And-XML-AJAX-
A set of Web Technology that sends and receive data from a server asyncronously.

- JSON (Java Script Object Notation) has replaced XML for the most part.
You can compare and see the advantages of JSON over XML :https://www.quora.com/What-are-the-advantages-of-JSON-over-XML



 Why do we choose AJAX ?

•	Ajax helps to pass the information without refreshing the page or causing any delay.
•	Request data from the server after reloading the page .
•	Receive data from the server after reloading the page’
•	Sends data to Server in background
 
AJAX calling can be done by Javascript Caaling or JQuery etc.
XMLHttpRequest (XHR)  Object

	API in form of Object ( Object i.e., properties and methods attached to it)
	Which is provided by (the object) the browser’s JS environment
	Methods transfer data between client/server
	Can be used with the other protocols other than HTTP
	Can used with data than XML (JSON, plain text)


The working of AJAX :
	JQuery
	Axios
	SuperAgent
	Fetch API
	Prototype
	Node Http
 
 
 AJAX - The XMLHttpRequest Object
The keystone of AJAX is the XMLHttpRequest object.

The XMLHttpRequest Object
All modern browsers support the XMLHttpRequest object.

The XMLHttpRequest object can be used to exchange data with a server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

Create an XMLHttpRequest Object
All modern browsers (Chrome, Firefox, IE7+, Edge, Safari Opera) have a built-in XMLHttpRequest object.

Syntax for creating an XMLHttpRequest object:

variable = new XMLHttpRequest();
Example
var xhttp = new XMLHttpRequest();


XMLHttpRequest Object Methods
Method	Description
new XMLHttpRequest()	Creates a new XMLHttpRequest object
abort()	Cancels the current request
getAllResponseHeaders()	Returns header information
getResponseHeader()	Returns specific header information
open(method,url,async,user,psw)	Specifies the request

method: the request type GET or POST
url: the file location
async: true (asynchronous) or false (synchronous)
user: optional user name
psw: optional password
send()	Sends the request to the server
Used for GET requests
send(string)	Sends the request to the server.
Used for POST requests
setRequestHeader()	Adds a label/value pair to the header to be sent
XMLHttpRequest Object Properties
Property	Description
onreadystatechange	Defines a function to be called when the readyState property changes
readyState	Holds the status of the XMLHttpRequest.
0: request not initialized 
1: server connection established
2: request received 
3: processing request 
4: request finished and response is ready
responseText	Returns the response data as a string
responseXML	Returns the response data as XML data
status	Returns the status-number of a request
200: "OK"
403: "Forbidden"
404: "Not Found"
For a complete list go to the Http Messages Reference
statusText	Returns the status-text (e.g. "OK" or "Not Found")

Send a Request To a Server
To send a request to a server, we use the open() and send() methods of the XMLHttpRequest object:

xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
Method	Description
open(method, url, async)	Specifies the type of request

method: the type of request: GET or POST
url: the server (file) location
async: true (asynchronous) or false (synchronous)
send()	Sends the request to the server (used for GET)
send(string)	Sends the request to the server (used for POST)



GET Requests
A simple GET request:

Example
xhttp.open("GET", "demo_get.asp", true);
xhttp.send();
In the example above, you may get a cached result. To avoid this, add a unique ID to the URL:

Example
xhttp.open("GET", "demo_get.asp?t=" + Math.random(), true);
xhttp.send();
If you want to send information with the GET method, add the information to the URL:

Example
xhttp.open("GET", "demo_get2.asp?fname=Henry&lname=Ford", true);
xhttp.send();
 
POST Requests
A simple POST request:

Example
xhttp.open("POST", "demo_post.asp", true);
xhttp.send();
To POST data like an HTML form, add an HTTP header with setRequestHeader(). Specify the data you want to send in the send() method:

Example
xhttp.open("POST", "demo_post2.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Henry&lname=Ford");
Method	Description
setRequestHeader(header, value)	Adds HTTP headers to the request

header: specifies the header name
value: specifies the header value
The url - A File On a Server
The url parameter of the open() method, is an address to a file on a server:

xhttp.open("GET", "ajax_test.asp", true);
The file can be any kind of file, like .txt and .xml, or server scripting files like .asp and .php (which can perform actions on the server before sending the response back).

Asynchronous - True or False?
Server requests should be sent asynchronously.

The async parameter of the open() method should be set to true:

xhttp.open("GET", "ajax_test.asp", true);
By sending asynchronously, the JavaScript does not have to wait for the server response, but can instead:

execute other scripts while waiting for server response
deal with the response after the response is ready
The onreadystatechange Property
With the XMLHttpRequest object you can define a function to be executed when the request receives an answer.

The function is defined in the onreadystatechange property of the XMLHttpResponse object:

Example
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    document.getElementById("demo").innerHTML = this.responseText;
  }
};
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();


XML Applications
1. The XML Document Used
2.Display XML Data in an HTML Table

