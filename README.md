# IGP & BGP

(to be continued...)

------------------
# IGRP then EIGRP

IGRP, Interior Gateway Routing Protocol, like RIP, it is a classful, distance_vector routing tool.

It is propietary of Cisco Router only.


                     192.168.1.0/24            192.168.2.0/24
                       Segment1                  Segment2

                           |                        |
                           |                        |
                           |                        |
                           e0                       e0
                           |                        |
                           R1                       R2
                            \                      /
                             s0                   s1
           192.168.3.0/24     \                  /     192.168.4.0/24 
             Segment3          \                /        Segment4          
                                \              /
                                 \            /
                                  s1         s0
                                    \       /
                                        R3
                                       
                                        |
                                       to0
                                        |
                                        |
                                        |
                                                
                                    Segment5 
                                  192.168.5.0/24 
                                    
                                        |
                                        | 
                                        |  
                                       to0
                                        |
                                        R4
                                        |
                                        e0
                                        |
                                        |
                                        |
                                        
                                     Segment6
                                   192.168.6.0/24 





the features of Routes:

* Bandwidth

* Total Delay

# Display in Header of IP datagram

(to do)

# Advertisable Addr Type

(to do)

# LB

(to do)

# Unicast Routing Update in Entry of Routing Table

(to do)

------------------
# EGP then BGP

