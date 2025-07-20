# Service Script

This markdown provides a simple script and guide to create and manage a custom systemd service on **Ubuntu**.

---

## Step-by-Step Script to Create a Service

### 1. Create Your Executable Script

Save your script, for example:

```bash
#!/bin/bash

echo "Service is running..."
sleep infinity
```

Save as `my_script.sh` and make it executable:

```bash
sudo cp my_script.sh /usr/local/bin/my_script.sh
sudo chmod +x /usr/local/bin/my_script.sh
```

> 🛑 Make sure the path is absolute and accessible by root/systemd.

---

### 2. Create a systemd Service File

Create a new service file:

```bash
sudo nano /etc/systemd/system/my_service.service
```

Paste the following content:

```ini
[Unit]
Description=My Custom Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/my_script.sh
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

---

### 3. Reload and Start the Service

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable my_service
sudo systemctl start my_service
```

---

### 4. Check Status and Logs

```bash
sudo systemctl status my_service
journalctl -u my_service -f
```

---

## Summary

| Command                       | Purpose                        |
| ----------------------------- | ------------------------------ |
| `systemctl daemon-reexec`     | Reload systemd binary          |
| `systemctl daemon-reload`     | Reload unit files              |
| `systemctl enable my_service` | Enable service at boot         |
| `systemctl start my_service`  | Start the service immediately  |
| `systemctl status my_service` | View service status            |
| `journalctl -u my_service -f` | View service logs in real-time |

---
