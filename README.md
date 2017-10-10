# Implement ACK division attack in ns-3
## Course Code: CO300
## Assignment: #35
### Overview 
TCP uses a byte granularity error control protocol and consequently each TCP segment
is described by sequence number and acknowledgment fields that refer to byte offsets within
a TCP data stream. However, TCP's congestion control algorithm is implicitly defined in terms
of segments rather than bytes. This mismatch results in an attack called ACK-DIV, where the
receiver makes the sender to send data packets quicker.

### References
* TCP Congestion Control with a Misbehaving Receiver (https://cseweb.ucsd.edu/~savage/papers/CCR99.pdf)
* TCP models in ns-3: https://www.nsnam.org/docs/models/html/tcp.html
