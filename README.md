# 🔄 MAC Address Changer

A simple Bash script to change the MAC address of your Linux system to a random, valid one every time you run it. Perfect for privacy-conscious users who want to randomize their MAC address when connecting to new networks.

## ✨ Features

- Generates a **valid MAC address** using real OUI (Organizationally Unique Identifier) prefixes
- Randomizes the device-specific portion of the MAC address
- Simple one-command execution
- Works with both Ethernet (`eth0`) and Wi-Fi (`wlan0`) interfaces

## 📋 Prerequisites

- Linux-based operating system
- `macchanger` utility
- Root/sudo privileges

## 🚀 Installation

1. **Install macchanger** (if not already installed):

   ```bash
   sudo apt install macchanger -y
   ```

2. **Clone the repository**:

   ```bash
   git clone https://github.com/n1n7u70/Mac-address-changer.git
   ```

3. **Navigate to the directory**:

   ```bash
   cd Mac-address-changer
   ```

4. **Make the script executable**:

   ```bash
   chmod +x mac.sh
   ```

## 💻 Usage

Run the script with sudo privileges:

```bash
sudo ./mac.sh
```

The script will automatically:
1. Generate a list of valid OUI prefixes
2. Select a random OUI prefix
3. Generate random bytes for the device portion
4. Apply the new MAC address to your network interface

## ⚙️ Configuration

By default, the script is configured for Ethernet interfaces (`eth0`).

To use with a **Wi-Fi interface**, edit `mac.sh` and replace all instances of `eth0` with `wlan0`:

```bash
# Change these lines in mac.sh
ifconfig wlan0 down
macchanger -m "$ouimac:$uaamac" wlan0
ifconfig wlan0 up
```

## ⚠️ Disclaimer

This tool is intended for legitimate purposes such as privacy protection and network testing. Please use responsibly and in accordance with applicable laws and regulations.

## 📄 License

This project is open source and available for personal and educational use.

---

**⭐ Show some ❤️ and star the repo to support the project!**
