
---

## **🔹 Step 3 – Uploading the Code (PhantomTunnel.sh)**  

### **`PhantomTunnel.sh` – The Code Itself**  
```bash
#!/bin/bash
echo "[*] Starting PhantomTunnel – Invisible SSH Connection..."

MODE=${1:-"DNS"}  # Default to DNS tunneling
SERVER="your-hidden-server.com"
SSH_PORT="443"  # Uses HTTPS port for stealth

function start_dns_tunnel() {
    echo "[*] Tunneling SSH over DNS..."
    ssh -o ProxyCommand="ncat --proxy-type socks5 --proxy 127.0.0.1:9050 %h %p" -C -N -D 9050 user@$SERVER -p $SSH_PORT
}

function start_https_tunnel() {
    echo "[*] Tunneling SSH over HTTPS..."
    ssh -o ProxyCommand="openssl s_client -quiet -connect $SERVER:443" -C -N -D 9050 user@$SERVER -p $SSH_PORT
}

function start_icmp_tunnel() {
    echo "[*] Tunneling SSH over ICMP..."
    ssh -o ProxyCommand="ping -c 1 -p $(echo -n hello | xxd -p) $SERVER" -C -N -D 9050 user@$SERVER -p $SSH_PORT
}

if [[ "$MODE" == "DNS" ]]; then
    start_dns_tunnel
elif [[ "$MODE" == "HTTPS" ]]; then
    start_https_tunnel
elif [[ "$MODE" == "ICMP" ]]; then
    start_icmp_tunnel
else
    echo "Invalid mode. Use DNS, HTTPS, or ICMP."
fi
# A tunnel that is not seen is a tunnel that is never closed.
# A connection that does not exist is a connection that never ends.
# A system that does not ask for permission—will always have access.
# - V
