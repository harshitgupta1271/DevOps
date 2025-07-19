# 🧪 Selenium Grid Commands Cheat Sheet (v4.15.0)

## 📥 Step 1: Download Selenium Server

Download the required JAR from [[SeleniumHQ GitHub Releases](https://github.com/SeleniumHQ/selenium/releases)](https://www.selenium.dev/downloads/)  and place `selenium-server-4.15.0.jar` on the relevant machines.

---

## 🚀 Option A: Run in Standalone Mode (Single Machine)
## open cmd drom jar file location
```bash
java -jar selenium-server-4.15.0.jar standalone

Launches a single-machine Grid with both hub and node.

Access Grid UI at: http://localhost:4444

Option B: Hub & Node Setup (Multi-Machine / VM Setup)
🖥️ On Hub Machine

java -jar selenium-server-4.15.0.jar hub
Starts the hub server.

Grid UI available at: http://<hub-ip>:4444


On Node Machine
# Replace <hub-ip> with the actual Hub machine's IP
java -jar selenium-server-4.15.0.jar node --hub http://<hub-ip>:4444
Registers the node to the remote hub.

Verification
Open your browser and go to:
http://<hub-ip>:4444 or http://localhost:4444

Check for active sessions and node registrations
