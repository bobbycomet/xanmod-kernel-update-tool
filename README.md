# **XanMod Kernel Manager**

The XanMod Kernel Manager is a simple graphical tool to help you manage your XanMod kernel installations. This application makes it easy to install, update, and remove different XanMod kernel versions without needing to use complex terminal commands.

# **Note: This is an unofficial tool created by a community member. It is not affiliated with the official XanMod project. It is designed to work on Linux Mint and other Debian-based systems that use GTK for their graphical applications.**

# **Installation**

There are two easy ways to install the XanMod Kernel Manager.

# **Method 1: Direct .deb File**

If you just want to install the application, you can download the latest .deb file, named xanmodkernalmanager.deb, from the releases page and double-click it. Your system's package installer will handle the rest.

# **Method 2: APT Repository (Recommended)**

To receive automatic updates, it's best to add our official APT repository. This lets you install the application using a single command and keep it up to date whenever you run sudo apt update.

Add the GPG Key: This key verifies that the packages you download are from a trusted source.

#  **For the GPG Key command:**
    
        ```
        wget -qO - [https://raw.githubusercontent.com/bobbycomet/xanmod-kernel-update-tool/refs/heads/main/xanmodkernalmanager-repo/dists/stable/your-public-key.asc](https://raw.githubusercontent.com/bobbycomet/xanmod-kernel-update-tool/refs/heads/main/xanmodkernalmanager-repo/dists/stable/your-public-key.asc) | sudo gpg --dearmor -o /etc/apt/keyrings/xanmod-manager-repo.gpg
        ```

# **For the Add Repository command:**
  
        ```
        echo "deb [signed-by=/etc/apt/keyrings/xanmod-manager-repo.gpg] [https://bobbycomet.github.io/xanmod-kernel-update-tool](https://bobbycomet.github.io/xanmod-kernel-update-tool) stable main" | sudo tee /etc/apt/sources.list.d/xanmod-manager.list > /dev/null
        ```

# **For the Update and Install commands:**
   
        ```
        sudo apt update
        sudo apt install xanmod-kernel-manager
        ```
        ```

Once installed, you'll find the XanMod Kernel Manager in your application menu. Simply click to open it and use the graphical interface to manage your kernels. The application will handle the technical details for you!

# **Features**

Kernel Discovery: The application automatically detects and displays a list of all available and installed XanMod kernels by scanning the system's APT cache.

Active Kernel Identification: It identifies and tags the currently running kernel as "Active", preventing users from accidentally removing it.

Intuitive UI: The interface is divided into two panes: "Available XanMod Kernels" and "Installed (XanMod)", allowing for easy comparison and management. A search bar is included to filter the list of kernels.

Installation & Removal: You can select kernels from either pane to install or remove them. The tool handles the necessary apt commands in the background using pkexec for elevated privileges.

DKMS Integration: After a successful kernel installation, the manager automatically runs the necessary DKMS (Dynamic Kernel Module Support) commands to rebuild and install modules for the new kernel, ensuring hardware compatibility.

Automated Cleanup: The "Auto-Remove Old Kernels" feature helps maintain a clean system by automatically purging older, unused kernels. By default, it keeps the active kernel plus the two most recent versions.

Logging: All actions, including APT and DKMS output, are streamed to a log panel within the UI and saved to a log file (~/.config/xanmod-kernel-manager/logs/) for detailed review and troubleshooting.

System Notifications: When new XanMod kernels are available for update, the application can show a desktop notification to alert you. This check can be performed periodically.

Repo Management: If the official XanMod APT repository is not configured on the system, the application will offer to set it up automatically for you. This involves downloading the GPG key and creating the APT sources list file.

Persistent Settings: It remembers your preferred window size and position and saves the "auto-remove after install" setting for future use.



# **License**

This project is released under the MIT License, which means it's completely open-source. Feel free to use, modify, and share it.
