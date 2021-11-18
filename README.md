#fapsecure for macOS
*Contains an app blocker, you could block any apps that you want.
*Blocks Tor and other unsafe browsers
*It will enforce Cleanbrowsing family DNS (IPV4) by default on all versions of macOS. (Enforces SafeSearch and blocks porn)

A random password will be automatically generated on your desktop. You need to save that. If you lose the password, you'll have to wait for 4 hours to stop fapsecure.

Using a custom DNS (optional)
---------------------------
Fapsecure uses Cleanbrowsing family DNS by default, which is 185.228.168.168
If you want to use another DNS, then edit mydns.txt file in the fapsecure folder. It will be locked once you run fapsecure. To change it, you will have to stop fapsecure.

Installing
----------
Copy fapsecure folder to the Desktop (not optional) then paste the following command in "Terminal":

chmod +x ~/desktop/Fapsecure/Fapsecure.sh; ~/desktop/Fapsecure/Fapsecure.sh


The password for uninstalling fapsecure will be generated on your Desktop (fapsecurepw.txt), copy it immediately to lockbox.pluckeye.net

I am not responsible if you lose this password.

App Blocker
-----------
First you need to get the exact name of the binary of the app you want to block which is located in /Applications/exampleapp.app/Contents/MacOS

Here is how to get it:

Open Applications folder, right click the app that you want to block > Show package contents > Contents > MacOS, the binary file is located there, it has a black rectangle icon, Copy its file name exactly as it is and paste it in a new line in blockedapps.txt in the fapsecure folder, you could add as many apps as you want. The blocking is case-senstive which means that if the binary name is Telegram and you added telegram, the app won't be blocked. Also, don't put the binary file name between quotes even if it contains spaces.
Now run fapsecure, the app will be blocked. If you find another app, just add it to the list and run fapsecure again. You don't need to stop fapsecure to add apps.

Regex is used by default. If you add badapp, then badapp, badapplication and badapp 122345 will also be blocked. You can use the dollar sign ($) to mark the last character. Example: badapp$ will block only badapp

Fapsecure could be used to block access to specific pages of System Preferences by editing blockedapps.txt. This is very useful, if you want to enforce Screen Time settings while keeping your admin rights. Don't forget to also add the following 

Example:
-To block access to Screen Time pane, add:
com.apple.preference.screentime.remoteservice

-Also, add the following to block "Ignore Limit" button that let's you bypass Screen Time App Limits and DownTime:
ScreenTimeViewService

-To block access to Users & Groups, add:
com.apple.preferences.users.remoteservice

-To block access to Date & Time (added by default):
com.apple.preference.datetime.remoteservice

Uninstalling (and what to do if you forgot the password)
------------
A) If you have fapsecure's password:
Steps:

(Older fapsecure versions, used to install Cleanbrowsing DNS profile which could only be removed using fapsecure's password. You have to remove it. Go to System Preferences > Profiles then remove Cleanbrowsing profile by pressing the minus (-) button. Use fapsecure's password. Newer versions of fapsecure don't install that profile anymore but you could still download and edit that profile as you wish)


Fapsecure folder must be on the desktop

Open "Terminal" from your applications and Enter the following codes:

chmod +x ~/desktop/Fapsecure/uninstall.sh; ~/desktop/Fapsecure/uninstall.sh


You will be asked for your user account's password first. 
Then you will be asked for Fapsecure's password. Copy it from lockbox.pluckeye.net and paste it using Command+v then press enter.

(You MIGHT NEED to restart your mac and run the uninstaller again to complete the uninstallation using the same command above. The uninstaller will tell you if a restart is required)

A) If you don't have fapsecure's password:


Fapsecure folder must be on the desktop

Open "Terminal" from your applications and Enter the following codes:

chmod +x ~/desktop/Fapsecure/uninstalltime.sh; ~/desktop/Fapsecure/uninstalltime.sh

You'll have to wait for 4 hours then the uninstaller will remove fapsecure. Do not close the terminal window.


