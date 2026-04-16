# SDN-Based Firewall using Mininet

## Objective

To develop a controller-based firewall to block or allow traffic between hosts using SDN principles.

---

##  Tools Used

* Mininet
* Open vSwitch
* Ubuntu

---

##  Steps Performed

1. Created network topology using Mininet
2. Verified connectivity using `pingall`
3. Applied OpenFlow rules using `ovs-ofctl`
4. Blocked traffic from h1 → h2
5. Allowed traffic to other hosts

---

## Commands Used

```
sudo mn --topo single,3
pingall

sudo ovs-ofctl -O OpenFlow13 del-flows s1
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=100,icmp,nw_src=10.0.0.1,nw_dst=10.0.0.2,actions=drop"
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=0,actions=normal"
```

---

##  Results

* h1 → h2 blocked
* h1 → h3 allowed

---

##  Screenshots

###  Topology

<img width="653" height="421" alt="Screenshot from 2026-04-16 17-49-43" src="https://github.com/user-attachments/assets/c31a5660-aada-497b-b694-c84a75af9007" />



### Pingall Before Firewall

<img width="665" height="387" alt="Pasted image" src="https://github.com/user-attachments/assets/fcf46d16-d8e9-4bd4-bf4e-e421d826f586" />


###  Firewall Rule Applied

<img width="1574" height="75" alt="Pasted image (2)" src="https://github.com/user-attachments/assets/670d1408-e829-4294-8de9-647ec573a88b" />


### Blocked Traffic (h1 → h2)

<img width="713" height="306" alt="Pasted image (3)" src="https://github.com/user-attachments/assets/274fd99d-d2c6-415a-9834-16829a6cb79d" />


### Allowed Traffic (h1 → h3)

<img width="1016" height="33" alt="Pasted image (4)" src="https://github.com/user-attachments/assets/b27999ec-8c4a-4413-8432-d60f04cb7bcb" />


---

## Conclusion

A firewall was successfully implemented using OpenFlow rules in Mininet. Traffic from h1 to h2 was blocked while allowing communication with other hosts, demonstrating effective SDN-based traffic control.
