================================================================================
                    ANDROID MANAGER PRO - USER GUIDE
================================================================================

Version: 1.0
Website: https://androidmanager.netlify.app/
Support: igneouslove@gmail.com

================================================================================
                           WHAT IS THIS?
================================================================================

Android Manager Pro is a FREE Windows application that transfers files between
your Android phone and PC 3X FASTER than Windows File Explorer.

WHY USE THIS?
- File Explorer freezes on large transfers? We don't.
- Transfer 10,000 photos without errors
- See real progress: "File 237 of 1,250"
- Lightning-fast ADB protocol (20-40 MB/s vs 12 MB/s)
- 100% privacy - no cloud, no data collection

================================================================================
                         QUICK START (5 MINUTES)
================================================================================

STEP 1: ENABLE USB DEBUGGING ON YOUR PHONE
-------------------------------------------

Android 11+:
1. Go to: Settings > About Phone
2. Tap "Build Number" 7 times (you'll see "You are now a developer!")
3. Go back to: Settings > Developer Options
4. Enable "USB Debugging"
5. Accept the popup when you connect USB cable

Android 10 and below: Same steps as above

Note: "Developer Options" location varies by manufacturer:
- Samsung: Settings > Developer Options
- Xiaomi: Settings > Additional Settings > Developer Options
- OnePlus: Settings > System > Developer Options


STEP 2: CONNECT YOUR PHONE
---------------------------

1. Connect phone to PC via USB cable
2. On phone: Select "File Transfer" or "MTP" mode (not "Charging only")
3. On phone: Accept "Allow USB debugging" popup (check "Always allow")
4. Run AndroidManagerPro.exe
5. Click "Check USB Connection"
6. Should show: "Connected via USB"


STEP 3: START TRANSFERRING
---------------------------

1. Click "Refresh" to see phone folders
2. Select folder (e.g., DCIM for photos)
3. Click "Pull (Phone to PC)" or "Push (PC to Phone)"
4. Choose destination/source folder
5. Watch progress bar with file counts!

DONE! That's it!

================================================================================
                              FEATURES
================================================================================

FREE FEATURES (Always Free):
-----------------------------
- USB file transfer (fast ADB protocol)
- Real-time progress tracking
- File counter (e.g., File 100 / 1,250)
- Transfer speed display (MB/s)
- Folder navigation and subfolder browsing
- Manual path entry
- Save transfer profiles
- Transfer history (last 20 transfers)
- Auto-retry on connection errors
- Skip cache/temp files option


PREMIUM FEATURES (Coming Soon - $15):
--------------------------------------
- Wi-Fi wireless transfer
- Scheduled automatic backups
- Batch operations (multiple folders at once)
- App backup and restore (.apk + data)
- Cloud upload integration
- Advanced file filters
- Priority email support

================================================================================
                    ADVANCED: WI-FI TRANSFER SETUP
================================================================================

NOTE: Wi-Fi transfer requires technical setup. USB is recommended for most 
users. Both phone and PC MUST be on the SAME Wi-Fi network.

--------------------------------------------------------------------------------
METHOD 1: ANDROID 11+ (Built-in Wireless Debugging) - RECOMMENDED
--------------------------------------------------------------------------------

STEP 1: Enable Wireless Debugging
1. Phone: Settings > Developer Options > Wireless Debugging > Turn ON
2. Tap "Wireless Debugging" to see details
3. Note the IP:PORT shown at top (e.g., 192.168.1.114:46809)

STEP 2: First-Time Pairing (One-time only)
1. On phone: Tap "Pair device with pairing code"
2. You'll see:
   - IP address (e.g., 192.168.1.114)
   - Port (e.g., 37295)
   - 6-digit pairing code (e.g., 123456)
3. On PC: Open Command Prompt and type:
   
   adb pair 192.168.1.114:37295
   
   (Replace with YOUR IP:PORT from phone)
4. Enter the 6-digit code when prompted
5. Success message: "Successfully paired"

STEP 3: Connect in App
1. Go back to "Wireless Debugging" main screen
2. Copy the IP:PORT shown at TOP (different from pairing port!)
3. In Android Manager Pro:
   - Check "Show Advanced Wi-Fi Settings"
   - Enter IP:PORT (e.g., 192.168.1.114:46809)
   - Click "Connect Wi-Fi"
4. Should show: "Connected via Wi-Fi"

IMPORTANT NOTES:
- Port number changes each time you toggle Wireless Debugging
- Connection drops when phone screen locks (Settings > Developer Options > 
  Stay Awake > ON to prevent this)
- After phone restart, Wireless Debugging turns OFF - enable again


--------------------------------------------------------------------------------
METHOD 2: ANDROID 10 AND BELOW (USB Required First Time)
--------------------------------------------------------------------------------

STEP 1: Enable TCP/IP Mode via USB
1. Connect phone via USB cable
2. Open Command Prompt on PC
3. Type: adb devices
   (Should show your device)
4. Type: adb tcpip 5555
   (Enables TCP mode on port 5555)

STEP 2: Find Phone's IP Address
1. On phone: Settings > About Phone > Status > IP Address
   OR
2. Settings > Wi-Fi > Tap connected network > IP Address
   Example: 192.168.1.105

STEP 3: Connect Wirelessly
1. On PC Command Prompt, type:
   
   adb connect 192.168.1.105:5555
   
   (Replace with YOUR phone IP)
2. Should see: "connected to 192.168.1.105:5555"
3. NOW you can unplug USB cable!
4. In Android Manager Pro:
   - Check "Show Advanced Wi-Fi Settings"
   - Enter: 192.168.1.105:5555
   - Click "Connect Wi-Fi"


--------------------------------------------------------------------------------
METHOD 3: USING "WIRELESS ADB" APP (Easiest for Old Android)
--------------------------------------------------------------------------------

STEP 1: Install App
1. Open Google Play Store on phone
2. Search: "Wireless ADB"
3. Install app by "Henry" (free, no root needed)

STEP 2: Enable in App
1. Open Wireless ADB app
2. Tap big "Enable" button
3. App will show: "192.168.1.105:5555" (your phone's address)

STEP 3: Connect in Android Manager Pro
1. Copy IP:PORT from Wireless ADB app
2. In Android Manager Pro:
   - Check "Show Advanced Wi-Fi Settings"
   - Paste IP:PORT
   - Click "Connect Wi-Fi"

DONE! No USB cable, no command prompt needed!


--------------------------------------------------------------------------------
WI-FI TROUBLESHOOTING
--------------------------------------------------------------------------------

Problem: "Connection refused (10061)"
Solution:
- Turn Wireless Debugging OFF then ON again
- Port number changes - use NEW port
- Make sure phone and PC on SAME Wi-Fi network
- Disable VPN on both devices

Problem: "No connection could be made"
Solution:
- Check both devices on same Wi-Fi (not guest network)
- Phone firewall might be blocking - disable temporarily
- Try restarting Wi-Fi on both devices

Problem: Connection keeps dropping
Solution:
- Settings > Developer Options > Stay Awake > ON
- Keep phone screen on during transfer
- Disable Wi-Fi sleep: Settings > Wi-Fi > Advanced > Keep Wi-Fi on

Problem: Can't find phone IP address
Solution:
- Settings > About Phone > Status
- Or download "WiFi Analyzer" app from Play Store
- Or check router admin panel for connected devices

Problem: Pairing code not working
Solution:
- Code expires after 1 minute - get new code
- Make sure typing code correctly (6 digits)
- Try disabling and re-enabling Wireless Debugging

================================================================================
                         TROUBLESHOOTING (USB)
================================================================================

Problem: "No devices detected"
-------------------------------
1. Check USB cable is connected properly
2. Try different USB port (USB 2.0 works better than 3.0 sometimes)
3. On phone: Make sure "USB Debugging" is enabled
4. On phone: Accept "Allow USB debugging" popup
5. On phone: Try changing USB mode to "File Transfer" or "MTP"
6. Unplug and replug USB cable
7. Restart phone
8. Try different USB cable (some cables are charge-only)


Problem: "Device unauthorized"
-------------------------------
1. Check phone screen for popup
2. Tap "Allow" and check "Always allow from this computer"
3. If no popup, disable and re-enable USB Debugging


Problem: Transfer fails midway
-------------------------------
1. App auto-retries 3 times (check "Auto-retry" is enabled)
2. Don't disconnect USB during transfer
3. Keep phone screen on (or enable "Stay Awake" in Developer Options)
4. Close other apps using ADB (Android Studio, etc.)


Problem: Very slow transfer speed
----------------------------------
1. Try different USB port
2. Use USB 2.0 instead of USB 3.0 (sometimes faster for phones)
3. Close File Explorer if open (MTP conflicts with ADB)
4. Restart ADB: Open Command Prompt, type:
   adb kill-server
   adb start-server


Problem: App crashes or freezes
--------------------------------
1. Close and restart the app
2. Restart phone
3. Reinstall the app
4. Contact support with error details

================================================================================
                           TIPS & TRICKS
================================================================================

SPEED TIPS:
-----------
- USB is faster than Wi-Fi (use USB for large transfers)
- Close File Explorer when using this app
- Disable antivirus temporarily for faster speeds
- Use "Skip cache/temp files" to avoid unnecessary files


NAVIGATION TIPS:
----------------
- Use "Open Subfolder" to browse deeper into folders
- Use "Go Back" to navigate up
- Manual path entry: Type "/sdcard/DCIM/Camera" for direct access
- Save profiles for frequently used paths


SAFETY TIPS:
------------
- Always backup important files before factory reset
- Don't disconnect USB during transfer
- Check "Skip cache" to avoid transferring junk files
- Verify transfer completed (100%) before deleting from phone


COMMON PATHS:
-------------
Photos/Camera: /sdcard/DCIM/Camera
Screenshots: /sdcard/DCIM/Screenshots or /sdcard/Pictures/Screenshots
WhatsApp Media: /sdcard/WhatsApp/Media
Downloads: /sdcard/Download
Music: /sdcard/Music
Documents: /sdcard/Documents

================================================================================
                         SYSTEM REQUIREMENTS
================================================================================

PC Requirements:
- Windows 10 or Windows 11
- 50 MB free disk space
- USB port (for USB mode)
- Wi-Fi (for wireless mode)

Phone Requirements:
- Android 5.0 or higher
- USB Debugging capability
- USB cable (for USB mode)
- Same Wi-Fi network as PC (for wireless mode)

================================================================================
                              FAQ
================================================================================

Q: Is this safe? Will it damage my phone?
A: 100% safe. Uses official Android ADB protocol. Same technology used by
   developers worldwide. No root required, no system modifications.

Q: Why do I need to enable USB Debugging?
A: USB Debugging allows ADB protocol access. It's the only way to get fast,
   reliable transfers. Without it, you're stuck with slow MTP (File Explorer).

Q: Does this work with iPhone?
A: No, iPhone doesn't support ADB. Use iTunes or AirDrop for iPhone.

Q: Is my data private? Do you collect anything?
A: 100% private. No internet connection needed. No data collection. No cloud.
   Everything stays between your phone and PC only.

Q: Can I transfer apps?
A: Currently no. Premium version (coming soon) will support app backup/restore.

Q: Does this work with all Android brands?
A: Yes! Works with Samsung, Xiaomi, OnePlus, Google Pixel, Motorola, Oppo,
   Vivo, Realme, and all other Android phones.

Q: Why is it faster than File Explorer?
A: File Explorer uses MTP protocol (designed in 2008, slow and buggy).
   We use ADB protocol (modern, fast, reliable). 3x speed difference.

Q: Do I need to keep the app running?
A: Only during transfers. You can close it when done.

Q: How do I uninstall?
A: Just delete the .exe file. No installation files, no registry changes.

Q: Can I use multiple phones?
A: Yes! Connect one at a time via USB, or multiple via Wi-Fi (different ports).

================================================================================
                         TECHNICAL INFORMATION
================================================================================

Technology: Android Debug Bridge (ADB) protocol
License: ADB is Apache License 2.0 (bundled with permission)
Data Collection: None
Internet Required: No (except for cloud upload feature - coming soon)
File Size: ~30 MB (includes ADB binaries)
Source Code: [GitHub link if open source]

Supported Transfer Speeds:
- USB 2.0: 20-30 MB/s
- USB 3.0: 30-40 MB/s
- Wi-Fi: 15-25 MB/s (depends on router)

Compare to:
- File Explorer (MTP): 5-12 MB/s
- Smart Switch: 15-20 MB/s
- Cloud services: 5-10 MB/s (upload limited)

================================================================================
                            CHANGELOG
================================================================================

Version 1.0 (Current)
---------------------
- Initial release
- USB transfer support
- Wi-Fi transfer support (advanced)
- Progress tracking with file counts
- Folder navigation
- Profile saving
- Transfer history
- Auto-retry on errors

Coming in Version 1.1:
- Scheduled backups
- Batch operations
- App backup/restore
- Cloud upload integration
- Premium features

================================================================================
                           SUPPORT & CONTACT
================================================================================

Need Help?
----------
Email: [igneouslove@gmail.com]
Website: [https://androidmanager.netlify.app/]


Report Bugs:
------------
Please include:
1. Windows version
2. Phone model and Android version
3. Error message (screenshot if possible)
4. What you were trying to do

Feature Requests:
-----------------
We love feedback! Email us your suggestions.

================================================================================
                            LEGAL & LICENSE
================================================================================

Android Manager Pro: [Igneouslove - MIT/GPL/Proprietary]
Copyright (c) 2025 [Igneouslove]

This software includes Android Debug Bridge (ADB):
- Licensed under Apache License 2.0
- Copyright (C) The Android Open Source Project
- Full license: https://www.apache.org/licenses/LICENSE-2.0
- Source: https://android.googlesource.com/platform/packages/modules/adb/

Disclaimer:
This software is provided "as is" without warranty of any kind. Use at your
own risk. Always backup important data before transferring.

================================================================================
                          THANK YOU FOR USING!
================================================================================

If you find this tool helpful:
- Star us on GitHub
- Share with friends
- Leave a review
- Buy us a coffee: [Ko-fi/PayPal link]

Made with love by frustrated File Explorer users, for frustrated File Explorer users.

Happy transferring! 

================================================================================