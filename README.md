**`1.print ip address`**

Algorithm:
1.import all packages 
2.create IP client
3.initialize inet address class and create object IA
4.get ip address of system using GETLOCALHOST() method
4.print ip address

**`2.creation of date and time server`**
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

**`3.printing client address at server side`**
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

**`4.Creation of UDP server`**
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

**`5. Creation of a Simple Chat Program`**
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

**`DaemonThread`**
1. Declare DaemonThread class which extends Thread class.
2. Creating instances and passing string to the Daemon Thread constructor.
3. By using super() method in constructor, we are invoking the Thread() method
to create a thread with the name of the passed parameter to the constructor.
4. By using setDaemon(boolean), to make the current thread as daemon (or)
user thread. If boolean is true, then it set Current Thread to Daemon thread
otherwise it set to User Thread.
5. Using isDaemon() method, we are checking the thread is daemon or not.
6. Print the output.


**`7. http`**
Client.
Algorithm:
STEP 1: Create the URL with Http URL Connections
STEP 2: Define the Http Protocol for Client Connections.
STEP3: Get the Http Connection. STEP4:Print the URL for the Client.


**`8.file transfer`**

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

**`9.traceroute command:`**
1. Start the program.
2. Get the frame size from the user.
3. Create the frames.
4. Send frames to server.
5. If your frames reach the server, it will send ACK signal to client otherwise it
will send NACK(Negative ACK) signal to client.
6. Stop the program.


**`10. ping command`**
1. Start the program.
2. Define method runSystemCommand with one argument.
3. Create the sub process, execute system command.
4. Send a ping request to the loopback interface as a parameter to the
runSystemCommand method.
5. Print the result and date.
6. Stop the program.









Computer networks programs

1.print ip address



Algorithm:

1.import all packages 

2.create IP client

3.initialize inet address class and create object IA

4.get ip address of system using GETLOCALHOST() method

4.print ip address

Program:

import java.net.InetAddress;



class IPAddress

{

   public static void main(String args[]) throws Exception

   {

      

      InetAddress myIP=InetAddress.getLocalHost();

 

      System.out.println("My IP Address is:");

      System.out.println(myIP.getHostAddress());

  }

}





2.creation 0of date and time server

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

Program::

Client:

import java.io.*;

import java.net.*;

class dateclient

{

public static void main(String args[])

{

Socket soc;

DataInputStream dis;

String sdate;

PrintStream ps;

try

{

InetAddress ia=InetAddress.getLocalHost();

soc=new Socket(ia,8020);

dis=new DataInputStream(soc.getInputStream());

sdate=dis.readLine();

System.out.println("The data in the server is: "+sdate);

}

catch(IOException e)

{

System.out.println("The exception is: "+e);

}

}

}







Server:

import java.io.*;

import java.net.*;

import java.util.*;

class dateserver

{

public static void main(String args[])

{

ServerSocket ss;

Socket s;

PrintStream ps;

DataInputStream dis;

String inet;

try

{

ss=new ServerSocket(8020);

while(true)

{

s=ss.accept();

ps=new PrintStream(s.getOutputStream());

Date d=new Date();

ps.println(d);

ps.close();

}

}

catch(IOException e)

{

System.out.println("The exception is: "+e);

} } }





3.printing client address at server side

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



Server:

import java.io.*;

import java.net.*;

class Sip

{

public static void main(String args[])

{

ServerSocket ss;

Socket s;

DataInputStream dis;

String ip;

try

{

ss=new ServerSocket(8020);

while(true)

{

s=ss.accept();

dis=new DataInputStream(s.getInputStream());

ip=dis.readLine();

System.out.println("Ip address of the client system is"+ip);

}



}

catch(IOException e)

{

System.out.println("The exception is: "+e);

}

}

}





Client:

import java.io.*;

import java.net.*;

class Cip

{

public static void main(String args[])

{

Socket soc;

PrintStream ps;

try

{

InetAddress ia=InetAddress.getLocalHost();

soc=new Socket(ia,8020);

ps=new PrintStream(soc.getOutputStream());

ps.println(ia);

}

catch(IOException e)

{

System.out.println("The exception is: "+e);

}

}

}







4.

4.Creation of UDP server





Aim: To perform a java program for UDP client and server.





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



Server:

import java.net.*;

import java.io.*;

public class udpserver

{

public static int client=789;

public static int server=790;

public static void main(String arg[]) throws IOException

{

String s;

InetAddress id=InetAddress.getLocalHost();

BufferedReader dis=new BufferedReader(new InputStreamReader(System.in));

DatagramSocket ds=new DatagramSocket(server);

byte b[]=new byte[1024];

System.out.println("Server Side.... Sending....");

System.out.println("\n"+id);

while(true)

{

s=dis.readLine();

if(s.equals("end"))

{

b=s.getBytes();

DatagramPacket dp=new DatagramPacket(b,s.length(),id,client);

ds.send(dp);

break;

}

else

{

b=s.getBytes();

DatagramPacket dp=new DatagramPacket(b,s.length(),id,client);

ds.send(dp);

}

}

}

}





 Client:





import java.net.*;

import java.io.*;

public class udpclient

{

public static int client=789;

public static void main(String args[]) throws IOException

{

DatagramSocket ds=new DatagramSocket(client);

byte b[]=new byte[1024];

System.out.println("client....receiving....");

while(true)

{

DatagramPacket dp=new DatagramPacket(b,b.length);

ds.receive(dp);

String s=new String(dp.getData(),0,dp.getLength());

if(s.equals("end")) break;

else System.out.println(s);

}

}

}





5. Creation of a Simple Chat Program



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









Client program:







import java.io.*;

import java.net.*;

public class chatclient1

{

public static void main(String args[]) throws Exception

{

Socket sk=new Socket(InetAddress.getLocalHost(),2000);

BufferedReader sin=new BufferedReader(new InputStreamReader(sk.getInputStream()));

PrintStream sout=new PrintStream(sk.getOutputStream());

BufferedReader stdin=new BufferedReader(new InputStreamReader(System.in));

String s;

while ( true )

{

System.out.print("Client : ");

s=stdin.readLine();

sout.println(s);

s=sin.readLine();

System.out.print("Server : "+s+"\n");

 if ( s.equalsIgnoreCase("BYE") )

 break;

}

sk.close();

sin.close();

sout.close();

stdin.close();

}

}

Server program:





import java.net.*;

import java.io.*;

public class chatserver1

{

public static void main(String args[]) throws Exception

{

ServerSocket ss=new ServerSocket(2000);

Socket sk=ss.accept();

BufferedReader cin=new BufferedReader(new InputStreamReader(sk.getInputStream()));

PrintStream cout=new PrintStream(sk.getOutputStream());

BufferedReader stdin=new BufferedReader(new InputStreamReader(System.in));

String s;

while ( true )

{

s=cin.readLine();

 if (s.equalsIgnoreCase("END"))

 {

cout.println("BYE");

 break;

 }

System. out.print("Client : "+s+"\n");

System.out.print("Server : ");

s=stdin.readLine();

cout.println(s);

}

ss.close();

sk.close();

cin.close();

cout.close();

stdin.close();

}

}



6.DAEMON THREADS



Algorithm:







public class DaemonThread extends Thread

{

public DaemonThread(String name){

super(name);

}

public void run()

{

// Checking whether the thread is Daemon or not

if(Thread.currentThread().isDaemon())

{

System.out.println(getName() + " is Daemon thread");

}

else

{

System.out.println(getName() + " is User thread");

}

}

public static void main(String[] args)

{

DaemonThread t1 = new DaemonThread("t1");

DaemonThread t2 = new DaemonThread("t2");

DaemonThread t3 = new DaemonThread("t3");

// Setting user thread t1 to Daemon

t1.setDaemon(true);

// starting first 2 threads

t1.start();

t2.start();

// Setting user thread t3 to Daemon

t3.setDaemon(true);

t3.start();

}

}









exception

public class DaemonThread extends Thread

{

public void run()

{

System.out.println("Thread name: " + Thread.currentThread().getName());

System.out.println("Check if its DaemonThread: "

+ Thread.currentThread().isDaemon());

}

public static void main(String[] args)

{

DaemonThread t1 = new DaemonThread();

DaemonThread t2 = new DaemonThread();

t1.start();

// Exception as the thread is already started

t1.setDaemon(true);

t2.start();

}

}





7. http



Aim: Program to implement HTTP protocol and to print URl for the 



Client.



Algorithm:

STEP 1: Create the URL with Http URL Connections

STEP 2: Define the Http Protocol for Client Connections.

STEP3: Get the Http Connection. STEP4:Print the URL for the Client.



Program:



import java.io.*;

import java.net.*;

public class myhttp

{

public static void main(String args[])throws IOException

{

URL url=new URL("http://www.sathyabama.ac.in/");

URLConnection conn=url.openConnection();

conn.connect();

InputStreamReader content= new InputStreamReader(conn.getInputStream());

FileWriter f=new FileWriter ("abc.html");

for(int i=0;i!=-1;i= content.read())

{

f.write((char) i);

}

}

}



8.file transfer

8.file transfer

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

3. Initialize the BufferReader class for reading the client request (ie file name)

4. Initialize the FileReader class for reading the file.

5. Initialize Buffer Reader class for reading the file contents line by line.

6. Repeatedly read the file content line by line and send to the client through the socket S.

7. Close the socket stream, BufferedReader.



Program – Client



import java.net.*;

import java.io.*;

public class FTPClient

{

 public static void main( String args[ ] ) throws Exception

 {

 Socket s = new Socket(InetAddress.getLocalHost(), 4000);

 // reading the file name from keyboard. Uses input stream

 System.out.println("Enter the file name");

 BufferedReader keyRead = new BufferedReader(new InputStreamReader(System.in));

 String fname = keyRead.readLine();

// sending the file name to server. Uses PrintWriter

 OutputStream ostream = s.getOutputStream( );

 PrintWriter pwrite = new PrintWriter(ostream, true);

 pwrite.println(fname);

 // receiving the contents from server. Uses input stream

 InputStream istream = s.getInputStream();

 BufferedReader socketRead = new BufferedReader(new InputStreamReader(istream));

 String str;

 while((str = socketRead.readLine()) != null) // reading line-by-line

 {

 System.out.println(str);

 }

 pwrite.close(); socketRead.close(); keyRead.close();

 }

}



Program – Server



import java.io.*;

import java.net.*;

public class FTPServer

{

 public static void main(String args[]) throws Exception

 { // establishing the connection with the server

 ServerSocket ss = new ServerSocket(4000);

 System.out.println("Server ready for connection");

 Socket s = ss.accept(); // binding with port: 4000

 System.out.println("Connection is successful and wating for chatting");



 // reading the file name from client

 InputStream istream = s.getInputStream( );

 BufferedReader fileRead=new BufferedReader(new InputStreamReader(istream));

 String fname = fileRead.readLine( );

 // reading file contents

 BufferedReader contentRead = new BufferedReader(new FileReader(fname) );



 // keeping output stream ready to send the contents

 OutputStream ostream = s.getOutputStream( );

 PrintWriter pwrite = new PrintWriter(ostream, true);



 String str;

 while((str = contentRead.readLine()) != null) // reading line-by-line from file

 {

pwrite.println(str); // sending each line to client

 }

 s.close(); ss.close(); // closing network sockets

 pwrite.close(); fileRead.close(); contentRead.close();

 }

}



9.traceroute command:

Program:





import java.io.BufferedReader;

import java.io.InputStreamReader;

public class traceroutecmd

{

 public static void runSystemCommand(String command)

 {

 try

 {

 Process p = Runtime.getRuntime().exec(command);

 BufferedReader inputStream = new BufferedReader(

 new InputStreamReader(p.getInputStream()));

 String s = "";

 while ((s = inputStream.readLine()) != null)

 System.out.println(s);

 }

 catch (Exception e)

 {

 }

 }

 public static void main(String[] args)

 {

 // String ip = "www.google.co.in";

 // String ip = "127.0.0.1";

 String ip = "www.drranurekha.com";

 runSystemCommand("tracert " + ip);

 }

}





10. ping command



Ping command

Program:

import java.io.*;

public class ping1

{

public static void runSystemCommand(String Command)

{

try{

Process p=Runtime.getRuntime().exec(Command);

BufferedReader InputStream=new BufferedReader(new InputStreamReader(p.getInputStream()));

String s="vvv";

while((s=InputStream.readLine())!=null)

{

System.out.println(s);

}

}

catch(Exception e)

{

e.printStackTrace();

}

}

public static void main(String[]args)

{

String Ip="localhost";

runSystemCommand("ping " +Ip);

java.util.Date date=new java.util.Date();

System.out.println(date);

}

}





Case studies:

11

AIM:

To study the link state routing algorithm.

Link State routing:

Link state routing is a method in which each router shares its neighborhood’s knowledge with every other router in the internetwork. In this algorithm, each router in the network understands the network topology then makes a routing table depend on this topology.

Multipath routing techniques enable the use of multiple alternative paths. In case of overlapping/equal routes, the following elements are considered in order to decide which routes get installed into the routing table (sorted by priority): 

1. Prefix-Length: where longer subnet masks are preferred (independent of whether it is within a routing protocol or over different routing protocol 

2. Metric: where a lower metric/cost is preferred (only valid within one and the same routing protocol)

3. Administrative distance: where a lower distance is preferred (only valid between different routing protocols)

Advantages

Fast convergence: changes are reported immediately by the source affected

Robustness against routing loo

Router know the topology

Disadvantages

Significant demands on memory and processing resources

Requires very strict network design

Requires a knowledgeable network administrator

B

Vector state routing



In computer communication theory relating to packet-switched networks, a distance vector routing protocol is one of the two major classes of routing protocols, the other major class being the link-state protocol. Distance-vector routing protocol use the Bellman-Ford algorithm, Ford-Fulkerson algorithm, or DUAL FSM (in the case of Cisco Systems' protocols) to calculate paths.

A distance-vector routing protocol requires that a router informs its neighbors of topology changes periodically. Compared to link-state protocols, which require a router to inform all the nodes in a network of topology changes, distance-vector routing protocols have less computational complexity and message overhead.



Routers using distance-vector protocol do not have knowledge of the entire path to a destination. Instead they use two methods: 

1. Direction in which router or exit interface a packet should be forwarded.

2. Distance from its destination

Advantages:

Simplicity

Low resource requirements

Minimum link bandwidth

Disadvantages:

Slow convergence

Limited scalability

Potential for routing loops (coming)












