=TCP vs IP=
    We need difference layer so we can seperates things. For example, IP is used to set address, send data from address to another address
    Above IP we can user TCP or UDP
    IP protocol jobs is send data from address to address
    TCP is take care of ensuring reliable channel . Data is secured to be send in order. Without error ...
    The TCP layer has to split this data up into packets to give to the IP layer. 
    The TCP layer has to include sequence information in the packets to allow it to re-assemble them in the correct order at the far end, 
    and to detect if a packet has gone missing.
    It also needs to be able to resend a packet when this happens. 
    Finally the TCP layer sends additional packets to manage each connection, setting it up, terminating it, etc.

    https://www.quora.com/What-is-the-difference-between-TCP-and-IP-protocols

=TCP=
    3 ways handshake
    Client send Syn x(to mark the start of bit sent from client)
    Server send Syn Ack x+1 and y (to mark the start of bit send from server)
    Client send Ack x+1 y+1

    Syn x and y need to be random instead of 0 for some security

    Networking Book page 15

    Also send cwnd and rwnd => slow start. 
    cwnd help control bandwidth is not enough. rwnd control client or server capacity handling 

    If one of the packets is lost en route to the receiver, then all subsequent
packets must be held in the receiver’s TCP buffer until the lost packet is retransmitted
and arrives at the receiver. Because this work is done within the TCP layer, our appli‐
cation has no visibility into the TCP retransmissions or the queued packet buffers, and
must wait for the full sequence before it is able to access the data

    * Establish a connection between client and server first
    * Reliable to send the data to the destination
    * Make sure that packet will be sent in order
    * Provide flow control
    * Slow than UDP

=UDP=
    Used by DNS
    No guarantee of message delivery
    No guarantee of order of delivery
    No connection state tracking
    No congestion control

=NAT=
    is a mapping table from local address, port to router address, port

Bandwitdh:
    the capacity of a wired or wireless network communications link to transmit the maximum amount of data 
    from one point to another over a computer network or internet connection in a given amount of time

=REST vs RESTFUL=
    To differentiate or compare these 2, you should know what is REST.
    REST (REpresentational State Transfer) is basically an architectural style of development having some principles...
        It should be stateless
        It should access all the resources from the server using only URI
        It does not have inbuilt encryption
        It does not have session
        It uses one and only one protocol that is HTTP
        For performing CRUD operations, it should use HTTP verbs such as get, post, put and delete
    It should return the result only in the form of JSON or XML, atom, OData etc. (lightweight data )
    REST based services follow some of the above principles and not all
    RESTFUL services means it follows all the above principles.
