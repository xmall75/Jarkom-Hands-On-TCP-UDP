# Jarkom-Hands-On-TCP-UDP
Revanantyo Dwigantara<br />
5025211113<br />
Jarkom D<br />


<h1>TCP</h1>
<h2>1. What is the IP address and TCP port number used by the client computer (source) that is transferring the alice.txt file to gaia.cs.umass.edu?</h2>

![1](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/b15dba4f-9770-4c5e-a0a7-0655be64da5f)

IP address is 192.168.86.68<br />
source port is 55639<br />

<h2>2. What is the IP address of gaia.cs.umass.edu? On what port number is it sending and receiving TCP segments for this connection?</h2>

![1](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/739d2abe-e34a-4b2b-a2ad-2638cc057b94)

gaia IP address is 128.119.245.12<br />
source port is 80<br />

<h2>3. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu?. What is it in this TCP segment that identifies the segment as a SYN segment? Will the TCP receiver in this session be able to use Selective Acknowledgments (allowing TCP to function a bit more like a “selective repeat” receiver, see section 3.4.5 in the text)?</h2>

![3](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/2be30121-6183-4a64-8313-e98b3df0a84a)

sequence number (raw) : 4236649187<br />
flags : 0x002 (SYN).<br />
From the follow TCP stream there are no SACK options, so the following packet cannot use Selective Acknowledgments.


<h2>4. What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is it in the segment that identifies the segment as a SYNACK segment? What is the value of the Acknowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value?</h2>

![4](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/9dfda799-1cfd-4a73-af3b-acd9090ae19e)

sequence number (raw) : 1068969752.<br />
flags : 0x012 (SYN, ACK).<br />
The SYN-ACK flag value (0x12) is a result of setting both the SYN and ACK flags in the TCP header to 1 (indicating they are active), This is a standard part of the TCP protocol and is used to establish a connection in a reliable and synchronized manner.


<h2>5. What is the sequence number of the TCP segment containing the header of the HTTP POST command? How many bytes of data are contained in the payload (data) field of this TCP segment? Did all of the data in the transferred file alice.txt fit into this single segment?</h2>

![5](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/d91b2055-e351-4cba-97df-8826c5ad450a)

sequence number (raw) : 4236801228<br />
payload : 1385 bytes

<h2>6. Consider the TCP segment containing the HTTP “POST” as the first segment in the data transfer part of the TCP connection.</h2>
- At what time was the first segment (the one containing the HTTP POST) in the data-transfer part of the TCP connection sent?<br />
- At what time was the ACK for this first data-containing segment received?<br />
- What is the RTT for this first data-containing segment?<br />

![6](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/47c66f71-f651-4f7e-a569-cfe9e905704f)
![6v2](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/5dceb473-99b7-4b63-bdb4-37d1538add7f)

first segment arrival is at Feb 3, 2021 09:43:26.840557000 SE Asia Standard Time<br />
the response segment is at Feb 3, 2021 09:43:26.885500000 SE Asia Standard Time<br />
EstimatedRTT is more or less 0.449 second.

<h2>7. What is the length (header plus payload) of each of the first four data-carrying TCP segments?</h2>

![7v2](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/335c6e28-e3a5-4e81-8212-4680f3ee7d66)
![7](https://github.com/xmall75/Jarkom-Hands-On-TCP-UDP/assets/34641833/f924bb13-260c-4977-a8fc-31e36e5f87a1)

The first segment has length of 1437 bytes<br />
the response is 829 bytes

