# DNS over HTTPS (DoH) Setup Guide for OpenWrt/ImmortalWRT Routers

![OpenWrt Logo](https://openwrt.org/_media/logo.png)

## DNS-over-HTTPS-OpenWrt/ImmortalWRT

Welcome to the DNS over HTTPS (DoH) setup guide for your OpenWrt/ImmortalWRT router firmware! This comprehensive guide will walk you through the step-by-step process of configuring DNS over HTTPS on your router, enhancing your privacy and security while browsing the web.

### What is DNS over HTTPS (DoH)?

DNS over HTTPS is a protocol that encrypts your DNS queries using HTTPS, ensuring that your DNS requests are secure and private. By using DoH, you prevent third parties from intercepting or tampering with your DNS traffic, providing an additional layer of protection against potential threats.

### Prerequisites

- An OpenWrt/ImmortalWRT compatible router
- SSH access to your router

### Installation Steps

1. **SSH into your Router**

   First, open a terminal or command prompt and enter the following command, replacing `ROUTER-IPADDRESS` with the actual IP address of your router:
   ```
   ssh root@ROUTER-IPADDRESS
   ```
   Enter your router's root password when prompted.

2. **Update Package Lists**

   Once you have successfully logged in, update the package lists using the following command:
   ```
   opkg update
   ```

3. **Install Necessary Packages**

   Next, install the required packages by entering the following command:
   ```
   opkg install luci-app-https-dns-proxy
   ```
   This package will enable the HTTPS DNS Proxy feature on your router.

4. **Restart RPC Daemon**

   To ensure that the changes take effect, restart the RPC daemon by executing:
   ```
   /etc/init.d/rpcd restart
   ```

5. **Configure HTTPS DNS Proxy**

   Now that the necessary packages are installed, go back to your router's login page and log in again. Once logged in, navigate to `Services → HTTPS DNS Proxy` and configure the settings to your liking. You can specify the upstream DNS server, such as Cloudflare (1.1.1.1), Google (8.8.8.8), or any other DoH-enabled DNS server.


6. **Save and Apply**

   After configuring the settings, click on "Save & Apply" to activate the HTTPS DNS Proxy service on your router.

Congratulations! You have successfully set up DNS over HTTPS on your OpenWrt/ImmortalWRT router. Your DNS queries are now encrypted and protected from eavesdropping or manipulation.

### Additional Notes

- To ensure uninterrupted internet access, make sure your selected upstream DNS server is reliable and properly responds to DNS queries.
- If you encounter any issues, refer to the [OpenWrt/ImmortalWRT documentation](https://openwrt.org/docs/start) or seek help from the community.


### License

This guide is licensed under the [MIT License](https://opensource.org/licenses/MIT), allowing you to use, modify, and distribute it freely while providing attribution to the original authors.

### Acknowledgments

Special thanks to the OpenWrt/ImmortalWRT community and the developers of the `luci-app-https-dns-proxy` package for making this setup guide possible.

Happy and secure browsing! :lock_with_ink_pen:
