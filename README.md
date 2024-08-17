# CS745-Transparent-SSL-Proxy-Server
SSL or TLS is an application layer protocol for communication security. It allows two
communicating end-points to protect their communication from a third party. These two
communicating parties set up an encrypted tunnel between them. The encryption/decryption
of this communication tunnel is done using a symmetric key, which is negotiated using the
SSL/TLS protocol. SSL/TLS protocol requires the exchange of digital certificates to ensure
the authenticity of communicating parties to each other. Usually, a PKI is involved in
distributing digital certificates. PKI can be skipped if the two parties know each other’s digital
certificates by direct introduction.

# Experiment Setup

1. **Install VirtualBox**
2. **Install a Linux VM**  
   - Use a minimal package list (no graphical interface, but with an OpenSSH server).  
   - Let us call this VM `vm-nox-vanilla`.
3. **Install a Linux VM with graphical support**  
   - Only a browser is required, skip unnecessary packages, but ensure the OpenSSH server is installed.  
   - Let us call this VM `vm-gui-vanilla`.
4. **Clone `vm-nox-vanilla`**  
   - Clone into `vm-server-A` and `vm-proxy`.
5. **Clone `vm-gui-vanilla`**  
   - Clone into `vm-browser-1`.
6. **Now you have 3 VMs in VirtualBModify the proxy to act as a transparent SSL-proxyox:**  
   - One VM with Firefox (`vm-browser-1`).
   - One VM acting as a proxy with routing tables (`vm-proxy`).
   - One VM hosting the web server (`vm-server-A`).
7. **Network Setup**  
   - All communication between the browser (`vm-browser-1`) and the web server (`vm-server-A`) passes through the proxy (`vm-proxy`).
   - You may need to tweak the `NETWORK MANAGER` interface in your VirtualBox software for proper configuration.

# Experiment Tasks

1. **XSS Attack and Mitigation**
   - Task: Perform an XSS (Cross-Site Scripting) attack on the web server (`vm-server-A`) and implement a mitigation technique to prevent it.
   
2. **CSRF Attack and Mitigation**
   - Task: Execute a CSRF (Cross-Site Request Forgery) attack on the web application running on `vm-server-A` and implement mitigation strategies.

3. **Single-Sign-On Authentication**
   - Task: Set up and test Single-Sign-On (SSO) authentication for the web server. Ensure proper integration between browser, proxy, and server.

4. **Self-Signed Digital Certificates**
   - Task: Generate self-signed digital certificates on `vm-server-A` and configure the server to use these certificates for secure communication.

5. **Using Client-Side Digital Certificates**
   - Task: Configure the web server (`vm-server-A`) to authenticate clients using client-side digital certificates.

6. **Modify the Proxy for SSL Support**
   - Task: Modify the proxy VM (`vm-proxy`) to act as a transparent SSL-proxy, intercepting and forwarding encrypted traffic between the browser and the web server.

