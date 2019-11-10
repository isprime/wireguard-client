# wireguard-client


WireGuard is a secure network tunnel, operating at layer 3, implemented as a kernel virtual network interface for Linux, which aims to replace both IPsec for most use cases, as well as popular user space and/or TLS-based solutions like OpenVPN, while being more secure, more performant, and easier to use.


# Ububtu / Debian base

```
sudo add-apt-repository ppa:wireguard/wireguard
sudo apt-get update
sudo apt-get install resolvconf wireguard-dkms wireguard-tools linux-headers-$(uname -r)
```

More distros: https://www.wireguard.com/install/

