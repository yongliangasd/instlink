# instlink-releases

# InstLink: High-Performance P2P NAT Traversal & Service Gateway

**InstLink** is an all-in-one, ultra-fast remote access solution designed for Homelabbers and developers. It enables you to securely expose your internal services (NAS, Web, Gaming Servers, etc.) to the internet without the need for complex port forwarding or heavy relay servers.

### 🌟 Core Features
*   **True P2P NAT Traversal**: High-success rate TCP/UDP hole punching that connects you directly to your devices.
*   **Integrated DDNS**: Native support for Cloudflare and Aliyun to manage your public IP records automatically.
*   **Web Service Gateway**: A unified dashboard to manage and jump to all your remote services via clean URLs.
*   **Premium Management UI**: A modern, responsive web panel (Listening on `:15001`) for real-time traffic monitoring and task management.
*   **Extreme Performance**: Built with Go and a custom-optimized relay engine, capable of handling high-bandwidth scenarios (up to 10Gbps with minimal CPU overhead).

---

### 🚀 Installation Guide

InstLink is a single binary with zero dependencies. 

#### **Linux / macOS / OpenWrt**
1.  **Download** the binary for your architecture.
2.  **Install as a service**:
    ```bash
    chmod +x instlink
    sudo ./instlink install
    sudo ./instlink start
    ```
3.  **Access** the local management panel at `http://YOUR_IP:15001`.

#### **Windows**
1.  **Download** `instlink-windows-amd64.exe`.
2.  **Open CMD/PowerShell** as Administrator.
3.  **Run**:
    ```powershell
    .\instlink.exe install
    .\instlink.exe start
    ```
4.  **Access** the panel at `http://localhost:15001`.

---

### 🛡️ Why InstLink vs. Tailscale?

While Tailscale is a fantastic overlay VPN, **InstLink** is designed for a different set of priorities:

| Feature | InstLink | Tailscale |
| :--- | :--- | :--- |
| **Connection Model** | **Direct P2P Focus**: Prioritizes raw TCP/UDP port-to-port mapping. | **Mesh VPN**: Creates a virtual network interface (TUN/TAP). |
| **Latency** | **Ultra-Low**: Direct connection without the overhead of a virtual network driver. | **Moderate**: Encapsulation and virtual routing add slight latency. |
| **Relay Dependency** | **Zero Relay Design**: Designed to function without costly central relay servers (DERP). | **Relay Fallback**: Frequently falls back to DERP relays if P2P fails, which can be slow. |
| **Service Visibility** | **Public-facing**: Can map to public domains via integrated DDNS. | **Private-only**: Restricted to the Tailnet unless using Funnel (limited). |
| **Performance** | **1Gbps+ Native**: Optimized for high-throughput tasks like 4K streaming or large file transfers. | **CPU-Bound**: Encryption overhead often limits throughput on low-power devices. |

---

### 💡 Tips for Pro Users
*   **One-Click Binding**: Link your Agent to the Server instantly using a secure binding token.
*   **Traffic Stats**: Get real-time upload/download metrics for every single tunnel.
