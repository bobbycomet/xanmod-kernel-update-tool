*XanMod Kernel Manager*
The XanMod Kernel Manager is a simple graphical tool to help you manage your XanMod kernel installations. This application makes it easy to install, update, and remove different XanMod kernel versions without needing to use complex terminal commands.

Note: This is an unofficial tool created by a community member. It is not affiliated with the official XanMod project. It is designed to work on Linux Mint and other Debian-based systems that use GTK for their graphical applications.

*Installation*
There are two easy ways to install the XanMod Kernel Manager.

*Method 1: Direct .deb File*
If you just want to install the application, you can download the latest .deb file, named xanmodkernalmanager.deb, from the releases page and double-click it. Your system's package installer will handle the rest.

*Method 2: APT Repository (Recommended)*
To receive automatic updates, it's best to add our official APT repository. This lets you install the application using a single command and keep it up to date whenever you run sudo apt update.

*Add the GPG Key: This key verifies that the packages you download are from a trusted source.*

wget -qO - https://raw.githubusercontent.com/bobbycomet/xanmod-kernel-update-tool/main/your-public-key.asc | sudo gpg --dearmor -o /etc/apt/keyrings/xanmod-manager-repo.gpg


*Add the Repository: This command adds the XanMod Kernel Manager repository to your system's sources list.*

echo "deb [signed-by=/etc/apt/keyrings/xanmod-manager-repo.gpg] https://bobbycomet.github.io/xanmod-kernel-update-tool stable main" | sudo tee /etc/apt/sources.list.d/xanmod-manager.list > /dev/null


*Update and Install: Now, update your package list and install the application.*

sudo apt update
sudo apt install xanmodkernalmanager


*How to Use*
Once installed, you'll find the XanMod Kernel Manager in your application menu. Simply click to open it and use the graphical interface to manage your kernels. The application will handle the technical details for you. Add/remove/auto-remove. It does it. It will ask if you want to add the list of available xanmod kernels, just click yes, it may make you click yes twice, but after that, just choose your kernel. Also, if you see an orange exclamation, that just means you are not on a xanmod kernel, or it needs to be updated. When all is good, a green system tray icon appears.

*License*
This project is released under the MIT License, which means it's completely open-source. Feel free to use, modify, and share it.
