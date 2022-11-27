fapsecure for macOS
----------------------
*Includes an app blocker, you could block any apps that you want.
*Includes a file/folder protector, which could be used to protect any file/folder/app including the hosts file.
*Blocks Tor and other unsafe browsers
*It will enforce Cleanbrowsing family DNS (IPV4) by default on all versions of macOS. (Enforces SafeSearch and blocks porn)


A random password will be automatically generated on your desktop. You need to save that. If you lose the password, you'll have to wait for a delay 4 hours to stop fapsecure. You could customize the delay by editing delay.txt. You have to enter a delay in seconds.

Using a custom DNS (optional)
---------------------------
Fapsecure uses Cleanbrowsing family DNS by default, which is 185.228.168.168
If you want to use another DNS, then edit mydns.txt file in the fapsecure folder. It will be locked once you run fapsecure. To change it, you will have to stop fapsecure.

There is a bug on macOS when the DNS is locked. If you disconnect from a wifi network, you might not be able to reconnect. You'll have to go to Network Preferences> Wi-Fi> Advanced, then select your wifi network and click the minus button (-) to remove it then connect to it again. 

You could tell fapsecure to not touch the dns settings nor to lock it by putting nodns in the first line in mydns.txt

Installing
----------
Copy fapsecure folder to the Desktop (not optional) then paste the following line in "Terminal":

xattr -d com.apple.quarantine ~/desktop/Fapsecure/Fapsecure.sh; chmod +x ~/desktop/Fapsecure/Fapsecure.sh; ~/desktop/Fapsecure/Fapsecure.sh

(Copy using command + c, and paste using command + v)

The password for uninstalling fapsecure will be generated on your Desktop (fapsecurepw.txt), copy it immediately to lockbox.pluckeye.net

Please, do not lose it.

App Blocker
-----------
First you need to get the exact name of the binary of the app you want to block which is located in /Applications/exampleapp.app/Contents/MacOS

Here is how to get it:

Open Applications folder, right click the app that you want to block > Show package contents > Contents > MacOS, the binary file is located there, it has a black rectangle icon, Copy its file name exactly as it is and paste it in a new line in blockedapps.txt in the fapsecure folder, you could add as many apps as you want. The blocking is case-senstive which means that if the binary name is Telegram and you added telegram, the app won't be blocked. Also, don't put the binary file name between quotes even if it contains spaces.
Now run fapsecure, the app will be blocked. If you find another app, just add it to the list and run fapsecure again. You don't need to stop fapsecure to add apps.

Regex is used by default. If you add badapp, then badapp, badapplication and badapp 122345 will also be blocked. You can use the dollar sign ($) to mark the last character. Example: badapp$ will block only badapp

Fapsecure could be used to block access to specific pages of System Preferences by editing blockedapps.txt. This is very useful, if you want to enforce Screen Time settings while keeping your admin rights.
Example:
-To block access to Screen Time pane, add:
com.apple.preference.screentime.remoteservice

-Also, add the following to block "Ignore Limit" button that let's you bypass Screen Time App Limits and DownTime:
ScreenTimeViewService

-To block access to Users & Groups, add:
com.apple.preferences.users.remoteservice

-To block access to Date & Time (added by default):
com.apple.preference.datetime.remoteservice

File/folder Protection
---------------------
This could be done by editing protectedfiles.txt in fapsecure folder.
You could protect as many files/folders/apps as you want from being modified or deleted. If you add a folder, all of its contents will be protected.
Just add the paths to whatever you want to protect, and separate them using a line break(enter). Example:
/etc/hosts
/Applications/Wondershare.app
/Users/kiddo/Documents/confer.rtf 

Is there an easy way to get the path of a file or a folder?
Open Terminal and drag a file or folder to terminal and its path will appear in Terminal. Copy the path using ctrl+c and paste it into protectedfiles.txt

Another way to do it is by editing protectedfiles.txt using the nano editor. Enter this in terminal:
nano ~/Desktop/Fapsecure/protectedfiles.txt 

Now, you could just drag whatever file or folder to the terminal window and the path will be pasted into protectedfiles.txt. Press enter to insert a line break, drag another file if you want, repeat.
To save protectedfiles.txt, press: control+o, Enter, control+x

After you save protectedfiles.txt, you'll have to run fapsecure. You don't need to stop fapsecure to update the list protected files.

To unprotect the files, uninstall fapsecure.

Uninstalling (and what to do if you forgot the password)
------------
A) If you have fapsecure's password:
Steps:

(Older fapsecure versions used to install Cleanbrowsing DNS profile which could only be removed using fapsecure's password. You have to remove it. Go to System Preferences > Profiles then remove Cleanbrowsing profile by pressing the minus (-) button. Use fapsecure's password. Newer versions of fapsecure don't install that profile anymore but you could still download and edit that profile as you wish)


Fapsecure folder must be on the desktop

Open "Terminal" from your applications and Enter the following code:

xattr -d com.apple.quarantine ~/desktop/Fapsecure/uninstall.sh; chmod +x ~/desktop/Fapsecure/uninstall.sh; ~/desktop/Fapsecure/uninstall.sh


You will be asked for your user account password first. 
Then you will be asked for Fapsecure's password. Copy it from lockbox.pluckeye.net and paste it using Command+v then press enter.

(You MIGHT NEED to restart your mac and run the uninstaller again to complete the uninstallation using the same command above. The uninstaller will tell you if a restart is required)

A) If you don't have fapsecure's password:


Fapsecure folder must be on the desktop

Open "Terminal" from your applications and enter the following line:

xattr -d com.apple.quarantine ~/desktop/Fapsecure/uninstalltime.sh; chmod +x ~/desktop/Fapsecure/uninstalltime.sh; ~/desktop/Fapsecure/uninstalltime.sh

You'll have to wait for 4 hours then the uninstaller will remove fapsecure. Do not close the terminal window.


