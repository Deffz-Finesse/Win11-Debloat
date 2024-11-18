# AutoUnattend.xml: Your Ultimate Windows 11 Installation Automation Tool 🖥️✨

`AutoUnattend.xml` is a powerful automation file designed to streamline the installation of Windows 11, making the process faster, more efficient, and completely hands-free. Inspired by and partially generated using tools from [Schneegans Unattend Generator](https://schneegans.de/), it is packed with custom scripts, configurations, and optimizations that simplify setup while providing a clean, debloated, and optimized Windows environment.

## 🎯 Features at a Glance

### **General Installation Automation**
- Automates user creation, partitioning, and regional settings.
- Automatically accepts the Windows license agreement (EULA).
- Configures the system to bypass user prompts during installation.

### **Bypassing Hardware Requirements**
- Enables installation on systems that do not meet Windows 11's strict hardware requirements by:
  - Bypassing TPM checks.
  - Ignoring Secure Boot requirements.
  - Allowing systems with lower RAM than required.

### **User Account Setup**
- Creates a local administrator account with customizable username and password (`(CHANGE WITH NAME)` and `(CHANGE WITH PASSWORD)` placeholders).
- Enables automatic login for the first user session.

### **Removing Bloatware and Unnecessary Features**
- Scripts embedded in the file systematically remove:
  - **Apps**: Xbox, OneDrive, Feedback Hub, Paint3D, Cortana, Weather, and more.
  - **Capabilities**: Internet Explorer, Fax and Scan, Windows Media Player.
  - **Features**: PowerShell V2, Remote Desktop Connection, Math Recognizer.
  - A detailed list of removed items can be found in the `remove-packages.ps1`, `remove-caps.ps1`, and `remove-features.ps1` scripts.

### **System Tweaks and Optimizations**
- Configures Windows Explorer to open to "This PC" and enables classic context menus.
- Disables unnecessary startup sounds and widgets.
- Activates long file paths and disables UAC (User Account Control) for smoother operations.

### **Windows Update Control**
- Temporarily pauses Windows Updates to maintain system stability during post-installation configurations.

### **Customizing the Default User Profile**
- Applies default settings such as enabling hidden files and showing file extensions.
- Silences system notifications and disables app suggestions.
- Ensures consistent preferences for all users created on the system.

---

## 🛠️ How It Works

### **What It Does**
1. **Automates Installation**: Removes manual inputs during the setup process for a smooth installation.
2. **Bypasses Hardware Checks**: Registry edits are applied during the `windowsPE` pass to bypass TPM, Secure Boot, and RAM checks.
3. **Customizes Windows**: Runs a series of embedded scripts (`.ps1`, `.vbs`, `.xml`) to remove unwanted apps, apply system tweaks, and finalize the setup.
4. **Prepares the Default User Profile**: Configures default settings to ensure a consistent experience across user accounts.

### **How It Does It**
The process is divided into configuration passes:
- **`windowsPE`**: Handles initial setup tasks like hardware requirement bypass and user data configuration.
- **`specialize`**: Executes core customizations and scripts for removing bloatware, disabling features, and applying registry tweaks.
- **`oobeSystem`**: Finalizes the user setup, configures auto-logon, and applies first-logon commands.

Embedded scripts handle tasks like:
- **`remove-packages.ps1`**: Removes pre-installed apps (e.g., Xbox, Weather, OneDrive).
- **`remove-caps.ps1`**: Removes capabilities like Internet Explorer and Math Recognizer.
- **`remove-features.ps1`**: Disables Windows features like PowerShell V2 and Remote Desktop.

---

## 🚀 How to Use 🔧

### Prerequisites
1. **Download Windows 11 ISO**:
   - Obtain the latest ISO from [Microsoft's official site](https://www.microsoft.com/software-download/windows11).
2. **Bootable USB Creation Tool**:
   - Use a tool like [Rufus](https://rufus.ie/) to create a bootable USB drive.
3. **Text Editor**:
   - Use a text editor like Notepad or VS Code to modify the file.

### Steps
1. **Download and Clone**:
   ```bash
   git clone https://github.com/Deffz-Finesse/Debloated-Windows-11-Install.git
   ```
2. **Modify `AutoUnattend.xml`**:
   - Open `AutoUnattend.xml` and replace the placeholders:
     - `(CHANGE WITH NAME)` → Replace with your desired username.
     - `(CHANGE WITH PASSWORD)` → Replace with your password.
   - Save the file.
3. **Prepare the Bootable USB**:
   - Use Rufus to create a bootable USB drive with the Windows 11 ISO.
   - Copy the `AutoUnattend.xml` file to the **root directory** of the USB.
4. **Install Windows**:
   - Insert the USB into the target computer and boot from it.
   - The installation will proceed automatically, applying all configurations.

---

## 🧙 What It Removes and Why

### **Bloatware Apps** (via `remove-packages.ps1`)
- Microsoft Store apps like:
  - Clipchamp
  - Feedback Hub
  - Paint 3D
  - Sticky Notes
  - Xbox Game Bar
  - Weather
- Goal: Free up storage, improve performance, and reduce distractions.

### **Windows Capabilities** (via `remove-caps.ps1`)
- Internet Explorer
- Windows Media Player
- Fax and Scan
- Math Recognizer
- Goal: Remove legacy features to modernize the system.

### **Optional Windows Features** (via `remove-features.ps1`)
- PowerShell V2
- Remote Desktop Connection
- Snipping Tool
- Goal: Reduce resource usage and potential attack surfaces.

---

## 💡 Tips for Best Results

- **Test in a Virtual Machine**: Before deploying to physical hardware, test the configurations in a virtual environment like VirtualBox or VMware.
- **Backup Important Files**: Always back up critical data before performing a clean install.
- **Customize Further**: Modify the included scripts to add or remove features as needed.

---

## 🔗 Resources

- [Download Windows 11 ISO](https://www.microsoft.com/software-download/windows11)
- [Windows Answer File Reference](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-setup-automation-overview)
- [Unattend File Generator](https://schneegans.de/windows/unattend-generator/)

---

## 🙌 Contributions

Feel free to fork, submit issues, or open pull requests to improve this repository. Together, we can create the ultimate Windows installation experience.

---

Enjoy your journey to a faster, cleaner, and smarter Windows experience! 🚀
