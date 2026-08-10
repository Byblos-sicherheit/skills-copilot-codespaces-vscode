<!--
  <<< Author notes: Step 4 >>>
-->

## Step 4: DHCP Troubleshooting

_Excellent reservation work! :star:_

The most important skill is being able to diagnose problems when DHCP stops working. Let's learn the essential troubleshooting commands.

### Common DHCP Problems

| Problem | Symptoms | Likely Cause |
|---------|----------|--------------|
| No IP address | Device gets 169.254.x.x (APIPA) | DHCP server unreachable |
| IP conflict | Network instability | Overlapping ranges or static IP in pool |
| Wrong gateway | Can't reach internet | Misconfigured `option routers` |
| Lease not renewing | Intermittent connectivity | Short lease time or server down |
| Slow lease | Long connection time | DHCP pool exhausted |

### Essential Troubleshooting Commands

**On Linux clients:**
```bash
# Release current IP
dhclient -r eth0

# Request a new IP
dhclient eth0

# View current lease info
cat /var/lib/dhclient/dhclient.leases

# Check IP assignment
ip addr show
```

**On the DHCP server:**
```bash
# Check server status
systemctl status isc-dhcp-server

# View active leases
cat /var/lib/dhcpd/dhcpd.leases

# Test configuration file
dhcpd -t -cf /etc/dhcp/dhcpd.conf

# Watch DHCP traffic live
tcpdump -i eth0 port 67 or port 68

# View server logs
journalctl -u isc-dhcp-server -f
```

**Windows clients:**
```cmd
REM Release IP
ipconfig /release

REM Renew IP
ipconfig /renew

REM Flush DNS
ipconfig /flushdns

REM View all network info
ipconfig /all
```

### :keyboard: Activity: Create a Troubleshooting Script

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file: `dhcp/troubleshoot.sh`
1. Add the following diagnostic script:
   ```bash
   #!/bin/bash
   # DHCP Troubleshooting Script

   echo "=== DHCP Troubleshooting Tool ==="
   echo ""

   echo "[1] Current IP Configuration:"
   ip addr show
   echo ""

   echo "[2] DHCP Server Status:"
   systemctl status isc-dhcp-server --no-pager
   echo ""

   echo "[3] Active DHCP Leases:"
   cat /var/lib/dhcpd/dhcpd.leases 2>/dev/null || echo "No lease file found"
   echo ""

   echo "[4] Test DHCP Config:"
   dhcpd -t -cf /etc/dhcp/dhcpd.conf && echo "Config OK" || echo "Config ERROR"
   echo ""

   echo "[5] Recent DHCP Log Entries:"
   journalctl -u isc-dhcp-server --no-pager -n 20
   ```
1. Commit directly to `main`.

**Wait about 60 seconds then refresh your repository landing page for the next step.**
