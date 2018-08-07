# mtcp_latency

Some change from eunyoung14 mtcp example.

./epwget 10.0.0.11/example.txt 1 -N 1 -c 1 -f epwget.conf -m 10000

"-m" is the number of message to send.
Using only one core and one socket at same time to achieve minimum latency.
Send the next message after receiving the response from the server. 
10.0.0.11 is the ip address of the server's dpdk.
./epserver -p /users/yujiaxie/mtcp -f epserver.conf -N 1

#### To change the size of message, change the 
In epwget.c:
+ Line 81
+ Line 549
In epserver.c:
+ Line 101
+ Line 537
And change the buffer size in conf file to make the buffer large enough for long message.


