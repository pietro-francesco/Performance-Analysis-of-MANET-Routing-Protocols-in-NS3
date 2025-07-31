# Performance-Analysis-of-MANET-Routing-Protocols-in-NS3

This report presents a comparative analysis of the performance of AODV and DSDV routing protocols for mobile ad hoc networks (MANETs). 
The primary goal is to compare the performance of these protocols as the number of nodes in the network varies, while keeping mobility and traffic models constant. 
This analysis is crucial for understanding how these protocols behave under different network loads and for selecting the most appropriate protocol for a given application.

# MANET Routing Protocols
MANET routing protocols are mainly divided into reactive and proactive. Their fundamental differences lie in how they discover and maintain routes.
 - Reactive Protocols: These protocols, like AODV (Ad hoc On-Demand Distance Vector), discover paths only when it is actually necessary to send data. When a node needs to send a packet, it initiates a route discovery process by broadcasting a route request (RREQ).
 - Proactive Protocols: In contrast, proactive protocols like DSDV (Destination-Sequenced Distance-Vector Routing) constantly maintain routes to all possible destinations in the network. This is done through a combination of periodic updates, ensuring a path is always available when needed. DSDV is based on the Bellman-Ford algorithm.

# Simulation Setup and Metrics
The simulations were conducted in a 500m x 500m area for 300 seconds, varying the number of nodes (10, 15, 20, and 25). The performance metrics used for evaluation are:
 - Packet Delivery Ratio (PDR): The ratio of total packets delivered to the total number of packets sent from the source node.
 - Dropped Packets: The total number of packets that failed to reach their destination.
 - Average End-to-End Delay: The average time taken for a packet to travel from the source to the destination.

# Results and Analysis
The simulation results provide a clear comparison between the two protocols:
 - Packet Delivery Ratio (PDR): DSDV consistently shows a higher PDR than AODV, reaching a peak of nearly 1.0 (0.995) with 15 nodes. AODV's PDR peaks at 0.94 with 15 nodes but decreases in larger networks due to higher routing overhead and potential congestion.
 - Dropped Packets: AODV shows a higher number of dropped packets than DSDV in all scenarios. The greater number of dropped packets in AODV is attributed to the latency of route discovery.
 - Average End-to-End Delay: AODV presents a significantly higher end-to-end delay than DSDV. The high initial delay in AODV is due to the route discovery process that reactive protocols must perform. DSDV maintains a very low and stable delay because routes are already established.

# Conclusion
In summary, DSDV consistently outperforms AODV in terms of Packet Delivery Ratio, Average End-to-End Delay, and dropped packets. 
This is due to its proactive nature, where routes are maintained at all times, ensuring data can be transmitted with minimal delay and a higher probability of success. AODV, being a reactive protocol, suffers from higher delays and packet loss due to the latency associated with on-demand route discovery. For applications where high reliability (high PDR, low packet loss) and low latency are critical, DSDV appears to be the superior choice in the simulated scenarios.




