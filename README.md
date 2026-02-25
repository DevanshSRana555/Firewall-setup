A beginner-friendly guide to managing inbound traffic rules using the Windows Defender Firewall GUI.

## 📋 Prerequisites
- Windows 11
- Administrative Privileges

---

## 🚀 Step-by-Step Implementation

### 1. Open Firewall Configuration
Search for **"Windows Defender Firewall with Advanced Security"** in the Start Menu.
![Open Tool](./assets/screenshots/1Defender_Firewall_service.png)

### 2. List Current Rules
Click on **Inbound Rules** in the left-hand pane to view the active filter list.

### 3. Block Inbound Traffic (Port 23 - Telnet)
1. Click **New Rule...** in the Actions pane.
2. Select **Port** > **Next**.
3. Choose **TCP** and enter `23` in **Specific local ports**.
4. Select **Block the connection**.
![Block Rule](./assets/screenshots/2Block_Telnet.png)

### 4. Test the Rule
Open **Command Prompt** and run:
`telnet localhost 23`
**Expected Result:** Connection failure (timeout or refused).
![Test Proof](./assets/screenshots/3Connection_proof.png)

### 5. Restore Original State
Right-click your "Block Telnet" rule and select **Delete** to restore access.

---

## 🔍 How the Firewall Filters Traffic
The Windows Firewall acts as a gatekeeper using a **Rule-Based System**:
- **Port:** It identifies traffic by the "service door" number (e.g., 23).
- **Action:** It checks if there is a specific "Allow" or "Block" command for that door.
- **Priority:** Explicit "Block" rules always take priority over "Allow" rules in Windows.
