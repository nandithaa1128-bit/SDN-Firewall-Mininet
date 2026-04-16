# 🔥 SDN-Based Firewall using Mininet

## 📌 Objective

To develop a controller-based firewall to block or allow traffic between hosts using SDN principles.

---

## 🛠️ Tools Used

* Mininet
* Open vSwitch
* Ubuntu

---

## ⚙️ Steps Performed

1. Created network topology using Mininet
2. Verified connectivity using `pingall`
3. Applied OpenFlow rules using `ovs-ofctl`
4. Blocked traffic from h1 → h2
5. Allowed traffic to other hosts

---

## 💻 Commands Used

```
sudo mn --topo single,3
pingall

sudo ovs-ofctl -O OpenFlow13 del-flows s1
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=100,icmp,nw_src=10.0.0.1,nw_dst=10.0.0.2,actions=drop"
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=0,actions=normal"
```

---

## 📊 Results

* ❌ h1 → h2 blocked
* ✅ h1 → h3 allowed

---

## 📸 Screenshots

### 🔹 Topology

/home/nanditha/sdn-firewall/images/Pasted image (2).png

### 🔹 Pingall Before Firewall

/home/nanditha/sdn-firewall/images/Pasted image (3).png

### 🔹 Firewall Rule Applied

/home/nanditha/sdn-firewall/images/Pasted image (4).png

### 🔹 Blocked Traffic (h1 → h2)

/home/nanditha/sdn-firewall/images/Pasted image (5).png

### 🔹 Allowed Traffic (h1 → h3)

/home/nanditha/sdn-firewall/images/Pasted image.png

---

## 🧠 Conclusion

A firewall was successfully implemented using OpenFlow rules in Mininet. Traffic from h1 to h2 was blocked while allowing communication with other hosts, demonstrating effective SDN-based traffic control.
