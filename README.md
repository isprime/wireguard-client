# wireguard-client


WireGuard is a secure network tunnel, operating at layer 3, implemented as a kernel virtual network interface for Linux, which aims to replace both IPsec for most use cases, as well as popular user space and/or TLS-based solutions like OpenVPN, while being more secure, more performant, and easier to use.


# Ububtu / Debian base

```
sudo add-apt-repository ppa:wireguard/wireguard
sudo apt-get update
sudo apt-get install resolvconf wireguard-dkms wireguard-tools linux-headers-$(uname -r)
```

More distros: https://www.wireguard.com/install/


Create the client configuration file (/etc/wireguard/wg0.conf) using the template provided here.

```
[Interface]
Address = 10.100.100.2/32
PrivateKey = XXXXX

[Peer]
PublicKey = XXXX
Endpoint = x.x.x.x:51820
AllowedIPs = 0.0.0.0/0
PersistentKeepalive = 21
```

# Start / Stop wireguard
`wg-quick up wg0` `wg-quick down wg0`


# Check the status of the connection

```
root@oraculo:/etc/wireguard# wg
interface: wg0
  public key: XXXXXXXXXXXXXXXXXX
  private key: (hidden)
  listening port: 39047
  fwmark: 0xca6c

peer: XXXXXXXXXXXXXXXXXXX
  endpoint: x.x.x.x:51820
  allowed ips: 0.0.0.0/0
  latest handshake: Now
  transfer: 5.33 KiB received, 2.24 KiB sent
  persistent keepalive: every 21 seconds
```
