# Issue: No connectivity between LAN and Azure

---

## Symptoms

- ICMP requests failing
- No response from remote network

---

## Evidence

<p align="center">
  <img src="../screenshots/ping-fail.png" width="700">
</p>

<p align="center">
  <img src="../screenshots/tcpdump-icmp.png" width="700">
</p>

---

## Analysis

- ICMP traffic observed entering IPsec tunnel
- No return traffic from Azure
- Tunnel established but routing incomplete

---

## Root Cause

Missing or incorrect route propagation between:

- BGP (Azure ↔ pfSense)
- OSPF (pfSense ↔ LAN)

---

## Fix

- Adjusted routing advertisement
- Ensured proper route redistribution between BGP and OSPF

---

## Result

<p align="center">
  <img src="../screenshots/ping-success.png" width="700">
</p>

✅ End-to-end connectivity restored
