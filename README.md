# Implement ACK division attack in ns-3
## Course Code: CO300
## Assignment: #34
### Overview 
TCP uses a byte granularity error control protocol and consequently each TCP segment
is described by sequence number and acknowledgment fields that refer to byte offsets within
a TCP data stream. However, TCP's congestion control algorithm is implicitly defined in terms
of segments rather than bytes. This mismatch results in an attack called ACK-DIV, where the
receiver makes the sender to send data packets quicker.

### References
* TCP Congestion Control with a Misbehaving Receiver (https://cseweb.ucsd.edu/~savage/papers/CCR99.pdf)
* TCP models in ns-3: https://www.nsnam.org/docs/models/html/tcp.html

### Changes made to original ns-3.27

* Files Changed : 
1]	/src/internet/model/tcp-socket-base.cc
Changes :   * New if-else clause for ACK-div code and normal code
 			* Additional Loop for dividing ACKs
 			* Each ACK is divided into 536 ACKs
 			* New variable 'm_preSeq' to store the value of last actual ACK number
 			* Packet level implementation in 'processACK' instead of Byte level implementation 
2] /src/internet/model/tcp-socket-base.h
Changes :	* New variable 'm_ackDivEnabled' as user input to implement attack from command line

* New Examples added : 1]	NAME = tcp-ack-div.cc, PATH = /examples/tcp


### Execution Commands

For ACK-DIVISION attack implementation :
* ./waf --run "tcp-ack-div --maxBytes=0 --ackdiv=true"
