# The Ghost in the Machine

**Subject:** 12.5 Troubleshooting IP Connectivity

**Objective:** To apply the OSI model framework and Cisco IOS diagnostic commands to identify and resolve logic errors deliberately injected into a network topology.

## 1. Activity Description

The dynamic was structured as a **Silent Infiltration** scenario. Prior to the session, three network nodes (devices) were "sabotaged" with subtle configuration errors. The audience, acting as the Incident Response Team, had to utilize a systematic methodology to exorcise the "ghost" (the fault) from the machine.

## 2. Applied Troubleshooting Methodology

The report highlights the use of the **"Divide and Conquer"** approach, moving through the layers of the OSI model:

* **Physical Layer:** Verifying interface status (`up/down` and `line protocol`).
* **Data Link Layer:** Reviewing VLAN assignments, MAC address tables, and encapsulation.
* **Network Layer:** Diagnosing IP addressing, subnet mask mismatches, and static/dynamic routing issues.

## 3. Log of "Ghosts" (Injected Errors)

The following table details the specific faults introduced during the activity:

| Device | Injected Error (The Ghost) | Network Symptom | Detection Command |
| :--- | :--- | :--- | :--- |
| PC-01 | Subnet Mask Mismatch (e.g., /25 instead of /24). | Can ping local hosts, but cannot reach the Default Gateway. | `ipconfig / show ip interface` |
| Router-A | Inbound ACL blocking ICMP traffic. | Host is alive but does not respond to PING (Request Timed Out). | `show access-lists` |
| Switch-1 | Access port assigned to the wrong VLAN. | Physical link is up, but no communication with the Gateway. | `show vlan brief` |
| Host-02 | Default Gateway pointing to a non-existent IP. | Packets cannot be routed outside the local broadcast domain. | `route print / show ip route` |
