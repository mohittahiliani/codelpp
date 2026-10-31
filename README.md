# CoDel++ and FQ-CoDel++

This repository contains the Linux and ns-3 patches for CoDel++ and FQ-CoDel++.

# Command to enable CoDel++ in Linux

sudo tc qdisc add dev <interface_name> root codel pp

Example: sudo tc qdisc add dev enp4s0 root codel pp

Verify if CoDel++ is attached as the root qdisc on the interface using the command:

tc qdisc show

# Expected output

qdisc noqueue 0: dev lo root refcnt 2
qdisc codel 8002: dev enp4s0 root refcnt 2 limit 1000p target 5ms interval 100ms pp
qdisc noqueue 0: dev wlp5s0 root refcnt 2 

Command to change the root queue disc back to CoDel

sudo tc qdisc change dev interface_name root codel
