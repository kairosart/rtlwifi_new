Lenovo  IDEPAD-310 WIFI Card issue

From: https://sites.google.com/site/easylinuxtipsproject/reserve-7#TOC-The-rtlwifi_new-driver-from-lwfinger


The rtlwifi_new driver from lwfinger
9. For the following Realtek wifi chipsets you can install the rtlwifi_new driver package from lwfinger:
RTL8192CE, RTL8192SE, RTL8192DE, RTL8188EE, RTL8192EE, RTL8723AE, RTL8723BE and RTL8821AE.

Note: for the RTL8723BE chipset, it's sometimes not necessary to replace the driver, because the current driver can sometimes be fixed as described in the left column of this web page (item 3).

a. First establish internet connection by other means, for example by ethernet cable.

b. Launch a terminal window.
(You can launch a terminal window like this: *Click*)

c. Copy/paste the following command line into the terminal, in order to download and install the required build packages (the building tools with which you're going to build the driver):

sudo apt-get install git build-essential linux-headers-$(uname -r)

Press Enter. Your password will remain entirely invisible, not even dots will show, this is normal.

d. Download the actual driver (the construction kit) by means of git, with this command (use copy/paste):

git clone https://github.com/lwfinger/rtlwifi_new.git

Is the driver no longer available on github.com? Then get the driver from here (the driver as it was on June 19, 2016). Then unpack the zipped file in your home folder, because it's a compressed folder. Don't unpack it in the subfolder Downloads, because then the ensuing terminal commands won't work!

e. Now you're going to compile the required kernel module from the driver package. Copy/paste this line into the terminal, in order to enter the folder with the driver packages:

cd rtlwifi_new

And then run this command:

make

f. Finally, install the compiled module with this command:

sudo make install

g. Reboot your computer.

h. Your wifi should work better now: click on the icon of Network Manager in the system tray, in order to see the available wireless networks.

Note: do NOT install kernel updates or new kernels, because then you'll probably lose the driver again! So in Linux Mint I advise to disable the visibility of kernel updates in Update Manager (panel: Edit - Preferences - section Options). In Ubuntu I advise to pin Ubuntu to the current kernel (item 7, left column).
