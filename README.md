# VLC Web Remote Interface Themed

This repository contains a customized HTML file named mobile.html, which serves as a themed version of the original VLC mobile interface. This interface allows users to control VLC Media Player from any device connected to the same Wi-Fi network, providing a seamless and user-friendly experience for media playback

## Screenshots

![Alt text](demo.png)

## Table of Contents

- [Instructions for Replacing `mobile.html` in VLC](#instructions-for-replacing-mobilehtml-in-vlc)
- [Instructions for Accessing VLC Web Interface on Smartphones](#instructions-for-accessing-vlc-web-interface-on-smartphones)
- [How to Activate VLC's Web Interface](#how-to-activate-vlcs-web-interface)


## Instructions for Replacing `mobile.html` in VLC

### Step 1: Navigate to the VLC HTTP Folder

**Windows:**
- Open File Explorer and navigate to:
  ```
  C:\Program Files\VideoLAN\VLC\lua\http\
  ```

**macOS:**
- Open Finder, then go to:
  ```
  /Applications/VLC.app/Contents/MacOS/share/lua/http/
  ```

**Linux:**
- Open a terminal and navigate to:
  ```
  /usr/share/vlc/lua/http/
  ```

### Step 2: Backup the Existing `mobile.html`

1. Locate the file named `mobile.html` in the folder you just navigated to.
2. Make a copy of this file and save it in a secure location (e.g., your desktop or a dedicated backup folder). This step is crucial in case you need to restore the original file later.

### Step 3: Replace `mobile.html` with the New File

1. Download the new `mobile.html` file from the specified repository (ensure that you have the correct version).
2. Once downloaded, replace the existing `mobile.html` file in the VLC HTTP folder with the new one. You may need administrative privileges to do this, especially on Windows and macOS.

### Step 4: Restart VLC

1. Close VLC if it is currently running.
2. Reopen VLC to apply the changes.


## Instructions for Accessing VLC Web Interface on Smartphones

To control VLC Media Player from your smartphone using its web interface, follow these detailed steps to set it up properly.

### **1. Enable the VLC Web Interface**

1. **Open VLC Media Player.**
2. Go to the **Tools** menu and select **Preferences**.
3. In the bottom left corner, select **All** under "Show settings" to access advanced settings.
4. Navigate to **Interface** > **Main Interfaces**.
5. Check the box for **Web** to enable the HTTP interface.
6. Under the **Lua** section (a sub-branch of Main Interfaces), set a password for the Lua HTTP interface (remember this password).
7. Save your settings and restart VLC. You will be prompted to allow VLC through your firewall, which is necessary for the web server to run.

### **2. Allow Remote Access**

By default, the web interface is restricted to localhost, meaning it can only be accessed from the machine running VLC. To allow access from other devices:

1. Locate the `.hosts` file:
   - **Windows:** `C:\Program Files (x86)\VideoLAN\VLC\lua\http\.hosts`
   - **Mac OS X:** `/Applications/VLC.app/Contents/MacOS/share/lua/http/.hosts`
   - **Linux:** `/usr/share/vlc/lua/http/.hosts`
   
2. Open this file in a text editor with administrative privileges.
3. Uncomment the last two lines to allow access from all IP addresses (be cautious as this may pose security risks) or specify a range of IP addresses or individual IPs that you want to allow access.
4. Save the file and restart VLC.

### **3. Accessing the Web Interface**

1. **Find Your Computer's IP Address:**
   - On Windows, open Command Prompt and type `ipconfig`. Look for the IPv4 Address.
   - On Mac, go to System Preferences > Network and find your active connection's IP address.

2. On your smartphone, open a web browser and enter:
   ```
   http://<your-ip-address>:8080/mobile.html
   ```
   Replace `<your-ip-address>` with your computer's actual IP address.

3. You will see an alert prompting you for a username and password:
   - Leave the username field blank.
   - Enter the password you set earlier for the Lua HTTP interface.

4. After entering your credentials, you will gain access to the mobile web interface of VLC.

### **4. Bookmarking the Interface**

For easier access in the future, it is recommended to bookmark this page in your smartphone's browser.

### **Additional Notes**

- Ensure that both your smartphone and PC are connected to the same Wi-Fi network for successful communication.
- If you encounter issues accessing the web interface from your smartphone, verify that firewall settings on your computer allow incoming connections on port 8080.



> Note: The below is the Instruction to activate the VLC Web Interface...These are the taken from [azrafe7/vlc4youtube](https://github.com/azrafe7/vlc4youtube) and I didn't made this...Its a good step by step instruction so I mentioned it Here

## How to activate VLC's web interface
Did you know that VLC has a web interface? 

![vlc-web-interface.png](vlc-web-interface.png)


with it you can control the player remotely, say via a web browser, with your phone, or even from your programming language of choice.

The thing is that it's not enabled by default, but activating it is really simple.

As I said you'll need at least version 2.0 of VLC installed. Then to activate the interface follow these steps:

 **1.** open VLC

 **2.** go to `Tools->Preferences`

>   ![vlc-preferences.png](vlc-preferences.png)

 **3.** show `All` settings

>  ![vlc-show-all-settings.png](vlc-show-all-settings.png)

 **4.** select `Main interfaces` on the left, and tick the `Web` checkbox on the right

>  ![vlc-show-all-settings.png](vlc-main-interfaces.png)

**5.** **Done!**

To check that it is working just open a browser in the same computer running VLC and point it to [http://localhost:8080](http://localhost:8080).

You should see the web interface.


# Troubleshooting

If you get an authorization error, or are prompted for a login (as could be the case for VLC versions above 2.1), just:

 **1.** search for `lua` in VLC preferences dialog

>   ![vlc-search-lua.png](vlc-search-lua.png)

 **2.** and set a password for `Lua HTTP` there

>   ![vlc-web-interface-password.png](vlc-web-interface-password.png)

 **3.** reopen `localhost:8080` in your browser and insert the password when asked, **but remember to leave the `User Name` field blank!**

>   ![vlc-blank-user.png](vlc-blank-user.png)

VLC should be listening for incoming connections in port 8080 (restart VLC if it still doesn't work). 

> Note that VLC Web Interface will only available when VLC is running.


# References

 - [azrafe7/vlc4youtube](https://github.com/azrafe7/vlc4youtube)
 
