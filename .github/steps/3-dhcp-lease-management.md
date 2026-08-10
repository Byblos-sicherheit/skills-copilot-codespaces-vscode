<!--
  <<< Author notes: Step 3 >>>
-->

## Step 3: DHCP Lease Management & Reservations

_You configured a DHCP server! :rocket:_

Now let's learn about **DHCP reservations** — assigning a permanent IP address to a specific device based on its MAC address.

### Why Use Reservations?

- Servers, printers, and network devices need predictable IP addresses
- Easier to manage firewall rules when IPs don't change
- Combines the convenience of DHCP with the stability of static IPs

### DHCP Reservation Configuration

In ISC DHCP format, a reservation (called a "host declaration") looks like this:

```conf
host printer-office {
    hardware ethernet AA:BB:CC:DD:EE:FF;
    fixed-address 192.168.1.10;
    option host-name "printer-office";
}

host server-web {
    hardware ethernet 11:22:33:44:55:66;
    fixed-address 192.168.1.20;
    option host-name "server-web";
}
```

### Understanding DHCP Leases

DHCP servers track leases in a **lease database** (`/var/lib/dhcpd/dhcpd.leases`):

```
lease 192.168.1.105 {
    starts 1 2024/01/15 08:00:00;
    ends   2 2024/01/16 08:00:00;
    binding state active;
    hardware ethernet AA:BB:CC:11:22:33;
    client-hostname "laptop-user";
}
```

### :keyboard: Activity: Create DHCP Reservations

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file: `dhcp/reservations.conf`
1. Add reservations for at least two devices:
   ```conf
   # DHCP Static Reservations

   host router-main {
       hardware ethernet AA:BB:CC:DD:EE:01;
       fixed-address 192.168.1.1;
       option host-name "router-main";
   }

   host nas-storage {
       hardware ethernet AA:BB:CC:DD:EE:02;
       fixed-address 192.168.1.10;
       option host-name "nas-storage";
   }

   host printer-main {
       hardware ethernet AA:BB:CC:DD:EE:03;
       fixed-address 192.168.1.11;
       option host-name "printer-main";
   }
   ```
1. Commit directly to `main`.

**Wait about 60 seconds then refresh your repository landing page for the next step.**
