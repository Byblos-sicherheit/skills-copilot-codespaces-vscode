<!--
  <<< Author notes: Step 2 >>>
-->

## Step 2: Configure a DHCP Server

_Great work on DHCP fundamentals! :tada:_

Now let's learn how to configure a DHCP server using the **ISC DHCP Server** format (also used by many routers and network appliances).

### ISC DHCP Server Configuration Structure

A typical `dhcpd.conf` file contains:

```conf
# Global settings
default-lease-time 86400;       # 24 hours
max-lease-time 604800;          # 7 days
authoritative;

# Subnet declaration
subnet 192.168.1.0 netmask 255.255.255.0 {
    range 192.168.1.100 192.168.1.200;
    option routers 192.168.1.1;
    option domain-name-servers 8.8.8.8, 8.8.4.4;
    option domain-name "example.local";
}
```

### Key Configuration Directives

| Directive | Description | Example |
|-----------|-------------|--------|
| `subnet` | Defines a network scope | `subnet 192.168.1.0 netmask 255.255.255.0` |
| `range` | IP address pool | `range 192.168.1.100 192.168.1.200;` |
| `option routers` | Default gateway | `option routers 192.168.1.1;` |
| `option domain-name-servers` | DNS servers | `option domain-name-servers 8.8.8.8;` |
| `default-lease-time` | Default lease in seconds | `default-lease-time 86400;` |
| `max-lease-time` | Maximum lease in seconds | `max-lease-time 604800;` |
| `authoritative` | This server is the authority | `authoritative;` |

### :keyboard: Activity: Write a DHCP Server Configuration

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file: `dhcp/dhcpd.conf`
1. Add the following DHCP server configuration:
   ```conf
   # Global DHCP Settings
   default-lease-time 86400;
   max-lease-time 604800;
   authoritative;

   # LAN Subnet
   subnet 192.168.1.0 netmask 255.255.255.0 {
       range 192.168.1.100 192.168.1.200;
       option routers 192.168.1.1;
       option domain-name-servers 8.8.8.8, 8.8.4.4;
       option domain-name "local.network";
   }
   ```
1. Commit directly to `main`.

**Wait about 60 seconds then refresh your repository landing page for the next step.**
