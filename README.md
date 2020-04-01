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
                           * s0 *                 s1
           192.168.3.0/24     \                  /     192.168.4.0/24 
             Segment3          \                /        Segment4          
                                \              /
                                 \            /
                                * s1 *       s0
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
                                       to0 (token ring)
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

IGRP config for R1:

    interface Ethernet0
     ip addr 192.168.1.1 255.255.255.0
     
    interface Serail0
     ip addr 192.168.3."2" 255.255.255.0
     
    router igrp
      network 192.168.1.0
      network 192.168.3.0
      
 IGRP config for R2:
 
     interface Ethernet0
     ip addr 192.168.2.1 255.255.255.0
     
    interface Serail1
     ip addr 192.168.4.2 255.255.255.0
     
    router igrp
      network 192.168.2.0
      network 192.168.4.0
      
 IGRP config for R3:
 
     interface S0
       ip addr 192.168.4.1 255.255.255.0
     
     interface S1
       ip addr 192.168.3.1 255.255.255.0
     
     interface TO0
       ip addr 192.168.5.1 255.255.255.0
     
     routing igrp 1
       network 192.168.3.0
       network 192.168.4.0
       network 192.168.5.0
       
The Routing Table of R1:

     R1$show ip route
     
     C 192.168.1.0/24 is directly connected. E0
     C 192.168.3.0/24 is directly connected. S0
     I 192.168.2.0/24 [] via 192.168.3."1", S0
     I 192.168.4.0/24 [] via 192.168.3."1", S0
     I 192.168.5.0/24 [] via 192.168.3."1", S0
     I 192.168.6.0/24 [] via 192.168.3."1", S0
     
# Debug

     R3$ debug ip igrp transactions
     > IGRP protocol debugging is on
     
     ...

# Display in Header of IP datagram

The IGRP info is encapsulated in the IP datagrams, the specific info includes header & route entries. This datagrams are destined fir the Local Braodcast Addr 255.255.255.255.

Format is like this

|version|Opcode|Edition| AS|
|-------:|:------:|-------:|:---|
|    Subnet    |  Network  |   
|Exterior Network| Checksum|   
|  Route Entry  for Subnet |   
| Route Entry  for Network |
|Route Entry for Exterior Network|

# Advertisable Addr Type

(to do)

# LB

(to do)

# Unicast Routing Update in Entry of Routing Table

(to do)

------------------
# EGP then BGP

(omit...)

