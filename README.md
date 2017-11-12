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
1] TCP Congestion Control with a Misbehaving Receiver (https://cseweb.ucsd.edu/~savage/papers/CCR99.pdf)

2] TCP models in ns-3: https://www.nsnam.org/docs/models/html/tcp.html

### New Example added 

* NAME = tcp-ack-div.cc

* PATH = scratch


### Execution Commands

For ACK-DIVISION attack implementation :
* ./waf --run "tcp-ack-div --maxBytes=0 --ackdiv=true"

### Execution Environment

* Run Time = 3s

* Bandwidth = 5Gbps

* Delay = 100ms
