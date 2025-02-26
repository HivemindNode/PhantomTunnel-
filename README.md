# PhantomTunnel.sh  
_A hidden SSH tunneling script that bypasses firewalls and detection._  

### What It Does:  
- **Encapsulates SSH traffic inside DNS, HTTPS, or ICMP packets**  
- **Bypasses deep packet inspection (DPI) to remain undetected**  
- **Uses port-hopping techniques to avoid firewall blocks**  
- **Allows secure access even in restricted networks**  

### Who Is It For?  
_"A connection that is not seen is a connection that cannot be stopped."_  

### How to Use:  
1. Install **PhantomTunnel** on the client and server  
2. Start the hidden SSH tunnel:  
   ```bash
   sudo bash PhantomTunnel.sh --start
