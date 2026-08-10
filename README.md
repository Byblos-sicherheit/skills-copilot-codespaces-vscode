<!--
  <<< Author notes: Course header >>>
  Include a 1280x640 image, course name in sentence case, and a concise description in emphasis.
-->

# Learn DHCP

_Understand the Dynamic Host Configuration Protocol (DHCP) — how it works, how to configure it, and how to troubleshoot it._

<header>

<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
-->

## Step 1: DHCP Fundamentals — The DORA Process

_Welcome to "Learn DHCP"! :wave:_

**DHCP (Dynamic Host Configuration Protocol)** is a network management protocol used to automatically assign IP addresses and other network configuration parameters to devices on a network. Without DHCP, every device would need to be manually configured with a unique IP address.

### How DHCP Works — The DORA Process

DHCP uses a 4-step process known as **DORA**:

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
- **Default Gateway**: Network router address sent to clients
- **DNS Servers**: Name resolution servers sent to clients
- **Lease Time**: How long a client may use an assigned IP before renewal

### :keyboard: Activity: Document the DORA Process

**We recommend opening another browser tab to work through the following activities so you can keep these instructions open for reference.**

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file:
   ```
   dhcp/README.md
   ```
1. Add the following content to document your understanding of DHCP:
   ```markdown
   # DHCP Notes

   ## What is DHCP?
   DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses
   and network configuration to devices.

   ## DORA Process
   - **Discover**: Client broadcasts to find a DHCP server
   - **Offer**: Server offers an available IP address
   - **Request**: Client requests the offered address
   - **Acknowledge**: Server confirms the lease

   ## Key Terms
   - Lease: Temporary IP address assignment
   - Scope: Range of addresses the server can assign
   - Reservation: Static IP bound to a MAC address
   ```
1. Select **Commit directly to the `main` branch** and click **Commit new file**.

**Wait about 60 seconds then refresh your repository landing page for the next step.**

</header>

<footer>

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2024 Byblos Sicherheit &bull; [MIT License](https://gh.io/mit)

</footer>
