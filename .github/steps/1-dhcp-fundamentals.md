<!--
  <<< Author notes: Step 1 >>>
-->

## Step 1: DHCP Fundamentals — The DORA Process

_Welcome to "Learn DHCP"! :wave:_

**DHCP (Dynamic Host Configuration Protocol)** is a network management protocol used to automatically assign IP addresses and other network configuration parameters to devices on a network.

### How DHCP Works — The DORA Process

| Step | Message | Direction | Description |
|------|---------|-----------|-------------|
| 1 | **D**iscover | Client → Broadcast | Client broadcasts to find available DHCP servers |
| 2 | **O**ffer | Server → Client | Server offers an IP address from its pool |
| 3 | **R**equest | Client → Broadcast | Client requests the offered IP address |
| 4 | **A**cknowledge | Server → Client | Server confirms the IP lease to the client |

### Key DHCP Concepts

- **Lease**: A temporary assignment of an IP address with an expiry time
- **Scope**: A range of IP addresses a DHCP server can assign
- **Reservation**: A permanent IP assignment tied to a MAC address
- **DHCP Pool**: The collection of IP addresses available for assignment

### :keyboard: Activity: Document the DORA Process

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file: `dhcp/README.md`
1. Add content documenting the DORA process and key DHCP terms.
1. Make sure your file includes the word `Discover` and `Acknowledge`.
1. Commit directly to `main`.

**Wait about 60 seconds then refresh your repository landing page for the next step.**
