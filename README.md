# DevilTwin V3.0

## 🦅 The Ultimate WiFi Security Testing Framework for ESP8266

![ShadowHawk Pro](https://img.shields.io/badge/Version-3.3-blue)
![Platform](https://img.shields.io/badge/Platform-ESP8266-green)
![License](https://img.shields.io/badge/License-For_Educational_Use_Only-red)

**One Device. Endless Possibilities.**

ShadowHawk Pro is a powerful, all-in-one WiFi security testing tool built on the ESP8266 (NodeMCU). It combines multiple attack vectors, security testing features, and network utilities into a single, easy-to-use web interface.

---

## 📋 Table of Contents

- [Features](#-features)
- [Hardware Requirements](#-hardware-requirements)
- [Installation](#-installation)
  - [Method 1: Using Android Phone](#method-1-using-android-phone)
  - [Method 2: Using PC (ESP Web Tool)](#method-2-using-pc-esp-web-tool)
- [User Guide](#-user-guide)
  - [First Boot & Activation](#first-boot--activation)
  - [Web Dashboard](#web-dashboard)
  - [Attack Modes](#attack-modes)
- [Web Interface Guide](#-web-interface-guide)
- [Troubleshooting](#-troubleshooting)
- [Disclaimer](#-disclaimer)
- [Support the Project](#-support-the-project)

---

## 🚀 Features

### 🔥 Attack Modes
| Mode | Description |
|------|-------------|
| **💀 Deauth Attack** | Disconnect specific client from target network |
| **💀🔥 Deauth All** | Disconnect ALL devices from ALL networks simultaneously |
| **🎭 Evil Twin Attack** | Clone target network, capture passwords via fake login page |
| **⚡ Combo Attack** | Deauth + Evil Twin combined for maximum effectiveness |
| **📡 Beacon Flood** | Flood area with fake WiFi networks |

### 🛡️ Security Features
| Feature | Description |
|---------|-------------|
| **🛡️ Deauth Detector** | Detect deauthentication attacks in real-time with audio/visual alerts |
| **🛡️ Device Activation** | Secure activation system to prevent unauthorized use |

### 📶 Utility Features
| Utility | Description |
|---------|-------------|
| **📶 WiFi Extender** | Repeater mode with NAT - extend existing WiFi signal |
| **🔍 Hidden Network Scanner** | Detect hidden SSIDs using promiscuous mode |
| **⚡ Quick Scan** | Fast network discovery |
| **📋 Password Capture Log** | View all captured credentials |

### 🎨 User Interface
- **📱 Fully Responsive** - Works perfectly on phones, tablets, and computers
- **🌙 Dark Theme** - Professional, easy-on-the-eyes design
- **🎯 One-Click Controls** - Simple and intuitive
- **📊 Real-time Status** - Live attack monitoring

---

## 🛠️ Hardware Requirements

### Essential Components
| Component | Description | Purpose |
|-----------|-------------|---------|
| **NodeMCU (ESP8266)** | Main controller board | Brain of the device |
| **USB Cable** | Type-C or Micro-USB | Power & programming |
| **USB Power Source** | Power bank, adapter, or PC | Power supply |

### Optional Components (for better visual feedback)
| Component | Quantity | Purpose |
|-----------|----------|---------|
| **5V Buzzer** | 1 | Audio alerts |
| **RGB LEDs** | 3 | Status indicators |
| **1kΩ Resistors** | 3 | Current limiting for LEDs |
| **Jumper Wires** | As needed | Connections |

### Recommended Wiring Diagram



NodeMCU Pins → Components:
─────────────────────────────
D0 (GPIO16)  → LED (Red)
D1 (GPIO5)   → Buzzer
D2 (GPIO4)   → Deauth LED
D3 (GPIO0)   → Reset Button
D4 (GPIO2)   → Status LED

Connect:

· LED Anodes → Resistors (1kΩ) → GPIO Pins
· LED Cathodes → GND
· Buzzer + → GPIO Pin
· Buzzer - → GND



---

## 📥 Installation

### Pre-requisites
1. Download the firmware `.bin` file from the [Releases](https://github.com/yourusername/ShadowHawk-Pro/releases) page
2. Choose your preferred flashing method below

---

### Method 1: Using Android Phone

**Step 1: Install the App**
- Go to **Play Store**
- Search and install **[ESP32 Flasher](https://play.google.com/store/apps/details?id=esptool.app)**
- Open the app

**Step 2: Configure the App**
1. Select **ESP8266** chip (if not selected)
2. Click on first slot
3. Select the downloaded `.bin` file
4. Set Offset to: `0x0`
5. Leave other settings as default

**Step 3: Connect Device**
1. Connect NodeMCU to phone using **OTG Adapter + USB Cable**
2. Put NodeMCU in **Download Mode**:
   - Press and HOLD the **BOOT** button
   - Press the **RESET** button once
   - Release the **BOOT** button
3. Click **Flash** button in the app
4. Wait for 100% completion
5. Reset the device

---

### Method 2: Using PC (ESP Web Tool)

**Step 1: Connect & Identify Port**
1. Connect NodeMCU to PC via USB Cable
2. Put NodeMCU in **Download Mode** (same as above)
3. Open **Device Manager** (Windows) or `ls /dev/tty*` (Linux/Mac)
4. Note the COM Port number (e.g., COM3, /dev/ttyUSB0)

**Step 2: Open ESP Web Tool**
1. Open your browser
2. Go to: **[ESP Web Tool](https://esp.huhn.me/)**
3. Click **Connect** button
4. Select your COM Port
5. Click **Connect**

**Step 3: Flash Firmware**
1. Click **Select File**
2. Choose the downloaded `.bin` file
3. Keep Offset as `0`
4. Click **Program**
5. Wait for progress bar to reach 100%
6. Done!

---

## 📱 User Guide

### First Boot & Activation

**Step 1: Connect to the Device**


SSID: ShadowHawk-Setup
Password: shadowhawk



**Step 2: Open Web Interface**
- Open your browser
- Go to: **`192.168.4.1`**
- You'll see the Activation page

**Step 3: Activate the Device**
1. Enter your home WiFi SSID
2. Enter your home WiFi Password
3. Click **Activate Device**
4. Device will connect to internet and activate
5. After activation, device will restart

**Step 4: Access Full Features**


SSID: ShadowHawk (or your custom name)
Password: shadowhawk (or your custom password)



- Open browser
- Go to: **`192.168.4.1`**
- You now have full access to all features!

---

### Web Dashboard Overview

After activation, you'll see the main dashboard with these sections:

#### 📊 System Status Card
- Target information (SSID, Channel)
- Active status badges
- Attack mode indicator
- Network count

#### ⚔️ Attack Control Center
- 💀 **DEAUTH TARGET** - Disconnect specific network
- 💀🔥 **DEAUTH ALL** - Disconnect all networks
- 📡 **BEACON FLOOD** - Create fake networks
- 🎭 **EVIL TWIN** - Clone and capture passwords
- ⚡ **COMBO ATTACK** - Combined attack

#### ⚙️ Quick Settings
- 📶 **WiFi Extender** - Repeater mode
- 🛡️ **Attack Detector** - Detect deauth attacks
- 🔍 **Mode Switch** - Verify/Auto-Stop
- 📋 **Passwords** - View captured credentials

#### 📶 Discovered Networks
- Quick Scan button
- Hidden Network Scan button
- List of all discovered networks
- Select target button

---

## 🎯 Attack Modes - Detailed Guide

### 1. 💀 Deauth Attack
**Purpose:** Disconnect a specific client from a target network

**How to use:**
1. Scan for networks
2. Select your target
3. Click **DEAUTH TARGET**

**Effect:** The target device will be disconnected from its WiFi network

---

### 2. 💀🔥 Deauth All Attack
**Purpose:** Disconnect ALL devices from ALL networks in range

**How to use:**
1. Click **DEAUTH ALL** from dashboard

**Effect:** All WiFi devices in range will be disconnected

---

### 3. 📡 Beacon Flood Attack
**Purpose:** Flood area with fake WiFi networks

**How to use:**
1. Click **BEACON FLOOD**

**Effect:** Creates 20+ fake networks visible to all devices

---

### 4. 🎭 Evil Twin Attack
**Purpose:** Clone a network and capture passwords

**How to use:**
1. Scan and select target network
2. Click **EVIL TWIN**
3. When victims connect, they'll see a fake login page
4. Any entered password is captured

**Modes:**
- **Verify Mode:** Tests if password is correct (connects to real network)
- **Auto-Stop Mode:** Captures password and stops immediately

---

### 5. ⚡ Combo Attack
**Purpose:** Deauth + Evil Twin combined

**How to use:**
1. Scan and select target network
2. Click **COMBO ATTACK**
3. The device will simultaneously deauth and create evil twin

**Effect:** Faster password capture as victims are forced to reconnect

---

### 6. 🛡️ Deauth Detector
**Purpose:** Detect and alert when deauth attacks are happening

**How to use:**
1. Click **Attack Detector** from settings
2. Device will enter monitoring mode

**Effect:** 
- Visual: LED pulses
- Audio: Beep pattern
- Web: Alert message

---

### 7. 📶 WiFi Extender
**Purpose:** Extend existing WiFi signal (repeater mode)

**How to use:**
1. Go to **WiFi Extender** from settings
2. Enter:
   - **Uplink SSID** (your existing WiFi)
   - **Uplink Password**
   - **Extender SSID** (new network name)
   - **Extender Password**
3. Click **Start Extender**

**Effect:** Creates a new WiFi network that extends your internet

---

## 🌐 Web Interface Guide

### Navigation


🦅 ShadowHawk Pro - Professional Security Testing       

│  │ 📊 System Status             
│  │ Target: HomeNetwork           
│  │ CH: 6                          
│  │ 💀 Deauth: OFF  📶 Ext: OFF  
│  │ ⚔️ Attack Control Center     
│  │ [DEAUTH] [ALL] [BEACON]       
│  │ [EVIL] [COMBO]                

│  │ 📶 Discovered Networks          
│  │ [Quick Scan] [Hidden Scan]     
│  │ 1. HomeNetwork   [Select]      
│  │ 2. GuestNetwork  [Select]      



### Important URLs
| URL | Page |
|-----|------|
| `/` | Main Dashboard |
| `/admin` | Full Control Panel |
| `/captured` | View Captured Passwords |
| `/extender` | WiFi Extender Settings |

---

## ⚙️ Settings & Customization

### Change AP Name & Password
1. Go to **Admin Panel** (`/admin`)
2. Find **Access Point Configuration**
3. Enter:
   - New SSID name
   - New password (min 8 chars)
4. Click **Save & Restart Device**

### Hidden Network Mode
1. In Admin Panel
2. Check **"Hide this network from scan results"**
3. Save & Restart

### Evil Twin Mode Switching
- Click **Switch to Auto-Stop** or **Switch to Verify**
- **Verify Mode:** Tests password against real network
- **Auto-Stop Mode:** Captures and stops immediately

---

## 🔧 Troubleshooting

### Common Issues & Solutions

#### Issue: Device Not Found After Flashing
**Solution:**
1. Wait 30 seconds after power-on
2. Check WiFi list for "ShadowHawk-Setup"
3. If not found, press reset button
4. Re-flash firmware

#### Issue: Cannot Connect to Web Interface
**Solution:**
1. Ensure you're connected to the device's WiFi
2. Try `http://192.168.4.1`
3. Check if browser is caching - clear cache
4. Try incognito/private mode

#### Issue: Attacks Not Working
**Solution:**
1. Make sure you've selected a target
2. Check if you're in the right mode
3. Disable other attacks first
4. Restart the device

#### Issue: Extender Not Getting Internet
**Solution:**
1. Check uplink WiFi credentials
2. Ensure uplink WiFi has internet
3. Wait 30 seconds after starting
4. Check if NAT is working

---

## ⚠️ Disclaimer


 ⚠️  EDUCATIONAL & SECURITY TESTING ONLY            
                                                     
█  This firmware is designed for:                     
█  ✅ Educational purposes                            
█  ✅ Security research                              
█  ✅ Testing your own networks                      
█  ✅ Authorized penetration testing                                                                 
█  ❌ NOT for unauthorized access                    
█  ❌ NOT for illegal activities                     
█  ❌ NOT for disrupting public networks                                                               
█  Always obtain permission before testing.           
█  Use at your own risk.  
