**1.print ip address**

Algorithm:
1.import all packages 
2.create IP client
3.initialize inet address class and create object IA
4.get ip address of system using GETLOCALHOST() method
4.print ip address

**2.creation of date and time server**
Algorithm:
1.server:
1.create instances of socket and server socket class 
2.use 8020 port for tcp
3.make the printstreamobject connect to output stream using socket
4.get an instance of dateclass and write it in socket
5.get ip address of client using socket and GETINETADRESS()
2.Client:
1.create and instance for socket class with port  8020
2.create an object of datainputstream and make it to get data from server through socket
3.read the date object
4.print the obtained data

**3.printing client address at server side**
Algorithm:
Server:
1. Import all the required io and net packages
2. Create a class Sip
3. Initialize the classes ServerSocket and Socket and their respective objects.
4. Initialize the class DataInputStream for reading the data from socket through
getInputStream() method.
5. Establish the connection with client system using the client IP and port number 8020
6. Read the IP address from the socket
7. Print the IP address at the server
Client:
1. Import all the required io and net packages
2. Create a class Cip
3. Initialize the classes Socket and their respective objects.
4. Initialize the class PrintStream Class for writing data into the socket through
getOutputStream() method.
5. Get the IP address of the system using InetAddress class with getLocalHost() method.
6. Establish the connection with server system using the IP address and port number 8020
7. Write the IP address into the socket
8. If any exception arise, print the error.

**4.Creation of UDP server**
Algorithm:
SERVER:
1.Create a new Datagram Socket.
2.Create a new Datagram packet.
3.Create a message to be sent.
4.Convert into bytes
5.create a packet
6.send packet
7.wait for acknowledgement from client
8.print data from client
9.stop the program
CLIENT:
1. Create new Datagram Socket.
2.Create new Datagram packet.
3.Get the packet.
4.Print the content.
5.Create a new packet.
6.send to server
7.Stop the program. 

**5. Creation of a Simple Chat Program**
Algorithm:
server:
Create a new ServerThread using socket.
Create a new Thread using the ServerThread, and then call start on the thread.
In ServerThread, make ServerThread implement Runnable
Create the ServerThread constructor and add the method run.
Client:
n ClientThread make a private BufferedReader in to receive data from clients, and a PrintWriter to write to the client.
Create a getter for the PrintWriter
Initialize the PrintWriter in run with the socket's output stream, and the BufferedReader with a new InputStreamReader using the socket's input stream
Create a while loop in run that checks for any new input and prints the input to all clients using the list of ClientThreads and the getter for the PrintWriter

**DaemonThread**
1. Declare DaemonThread class which extends Thread class.
2. Creating instances and passing string to the Daemon Thread constructor.
3. By using super() method in constructor, we are invoking the Thread() method
to create a thread with the name of the passed parameter to the constructor.
4. By using setDaemon(boolean), to make the current thread as daemon (or)
user thread. If boolean is true, then it set Current Thread to Daemon thread
otherwise it set to User Thread.
5. Using isDaemon() method, we are checking the thread is daemon or not.
6. Print the output.


**7. http**
Client.
Algorithm:
STEP 1: Create the URL with Http URL Connections
STEP 2: Define the Http Protocol for Client Connections.
STEP3: Get the Http Connection. STEP4:Print the URL for the Client.


**8.file transfer**

Implement FTP using TCP
Algorithm
1. Create a file which has to be read by the server. Open a notepad, write the file contents
and save it in the program folder sample.txt.
2. Import the required io and net packages.
3. Initialized the socket class for communicate with the server with port number 4000.
4. Client specifies the file name to the server (eg. Sample.txt)
5. Initialize the BufferReader class to read the filename from the terminal.
6. Initialize the PrintWriter class to write and send the file name to the server through the
socket.
7. Initialize BufferReader class to read the file contents from the 
server.
8. Repeatedly read the data till end of file equals to empty.
9. Close the socket stream, filestream and BufferReader classes
10. End of the program.
Algorithm – Server
1. Import the required io and net packages.
2. Initialized the SeverSocket class and accept the client connection.
3. Initializ the BufferReader class for reading the client request (ie file name)
4. Initialize the FileReader class for reading the file.
5. Initialize Buffer Reader class for reading the file contents line by line.
6. Repeatedly read the file content line by line and send to the client through the socket S.
7. Close the socket stream, BufferedReader.

**9.traceroute command:**
1. Start the program.
2. Get the frame size from the user.
3. Create the frames.
4. Send frames to server.
5. If your frames reach the server, it will send ACK signal to client otherwise it
will send NACK(Negative ACK) signal to client.
6. Stop the program.


**10. ping command**
1. Start the program.
2. Define method runSystemCommand with one argument.
3. Create the sub process, execute system command.
4. Send a ping request to the loopback interface as a parameter to the
runSystemCommand method.
5. Print the result and date.
6. Stop the program.
