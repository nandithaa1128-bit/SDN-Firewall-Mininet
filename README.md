SDN-Based Firewall using Mininet
Objective
To develop a controller-based firewall to block or allow traffic between hosts using SDN principles.
Tools Used
•	Mininet
•	Open vSwitch
•	Ubuntu
Steps Performed
1.	Created network topology using Mininet
2.	Tested connectivity using pingall
3.	Applied OpenFlow rules using ovs-ofctl
4.	Blocked traffic from h1 to h2
5.	Allowed traffic to other hosts
Commands Used
sudo mn --topo single,3
pingall
sudo ovs-ofctl -O OpenFlow13 del-flows s1
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=100,icmp,nw_src=10.0.0.1,nw_dst=10.0.0.2,actions=drop"
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=0,actions=normal"
Results
•	h1 → h2 blocked 
•	h1 → h3 allowed 
Conclusion
Firewall successfully implemented using OpenFlow rules.
