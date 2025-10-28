# Spamcaster
Home of the Spamcaster Radio/EUD Chest Mount

I am still finishing uploading files/instructions/etc.

# Parts List
1x GL.iNet GL-AXT1800

1x Generic Phone Plate Carrier Mount (example: https://www.amazon.com/dp/B0DYTPWVCR)

2x u.fl to SMA Female pigtail (6 inch or shorter)

1x 5.5mm x 2.1mm Screw Lock DC Barrel Power Plug (example: https://www.amazon.com/dp/B08KQ7PP21)

1x 90 degree USB C Cable (cut and solder the red/black wires to the power plug/socket to make the power cord)

1x 50mm length M3 bolt

1x 35mm length M3 bolt

17x between 8mm - 12mm length M3 bolt

(Ideally, order all bolts as part of an assorted M3 bolt kit)

2x M3 nylon lock nut

17x M3 heat set insert

2x LMR-200 or equivalent cable, length as desired

2x 2.4GHz + 5GHz wifi antennas

Optional for Molle Seals:

4x 96817A220 Thread Forming Screw For Thin Plastic (https://www.mcmaster.com/products/torx-thread-forming-screws/steel-thread-forming-screws-for-thin-plastic/?s=torx-thread-forming-screws)

# Configuration
Do this before assembly!

You'll want to configure the wireless interfaces for 802.11s mesh, and also set up at least one interface as an access point. The instructions are more or less the same as setting up the Rocket M5 for mesh operation, but recent firmware versions include all necessary packages. You can get the Rocket M5 setup guide here:

https://teamawarenesskit.org/viewtopic.php?t=36

The AXT-1800 has 2 wireless radios (2.4GHz and 5GHz). There are two types of networks that we will need to set up. The first type is an Access Point. This is what your EUD (phone) will connect to in order to access the mesh network. You can also connect a laptop, tablet, etc. It appears like a regular wifi network. The second type is an 802.11s mesh network. This is what links all of the Spamcasters and other mesh devices together. You can set up one/both/neither of these types of networks on each of the wireless radios. There is likely a network speed benefit to having the Access Point on only one radio and the mesh network on the other radio. There is likely a reliability advantage to having the mesh network on both radios. There is a device compatibility advantage to having the Access Point on both radios, although *most* devices nowadays have both 2.4GHz and 5GHz capability. In this walkthrough, we will set up an Access Point on the 5GHz radio, an 802.11s mesh network on the 5GHz radio, and another 802.11s mesh network on the 2.4GHz radio. Screenshots coming soon!

This setup has been tested with AXT1800 firmware version 4.8.2 from GL.iNet.

You probably need to update your firmware, so grab a computer or laptop with an ethernet port and follow the instructions here: https://docs.gl-inet.com/router/en/4/faq/debrick/

For those knowledgeable about networking, the short version of the firmware update process is: plug in the ethernet cable, hold the reset button on the AXT1800, plug in the AXT1800 power, wait for 5 flashes and a solid light, then release. Set a static IP for your computer of 192.168.1.2 and open 192.168.1.1 in your browser. Upload the img file and wait for it to reboot. Set your IP back to automatic DHCP. If this doesn't make sense, follow the more in-depth instructions from that link.

Open the router config page 192.168.8.1

Set a password.

Wifi doesn't matter, we will change it anyway.

Skip the initial config popup with the X in the top right corner.

Go to Advanced Settings on the left and then install/open LuCI.

Log in with the password you just set (username is root).

Go to Network - Wireless from the top menu.

Remove all the preconfigured wifi networks.

Save and apply changes by clicking the icon at the top left and Save & Apply.

======== 5GHz Access Point ========

Add a wifi interface to the radio0 AC/AX/N device.

Configure it to either AX or N mode. Pick a channel. Recommend 20MHz width for longest range. All mesh devices must use the same settings here.

Leave Mode as Access Point.

ESSID is the wifi network name that EUDs and other devices can connect to.

Set Network to Lan.

Wireless Security tab - set WPA2-PSK and specify a Key (aka password).

Other settings as desired. Defaults have best device compatibility.

Save (FYI follow these same steps on the 2.4GHz radio1 if you want a 2.4GHz access point available).

======== 5GHz 802.11s Mesh ========

Add another interface to this same radio0 AC/AX/N device.

SPECIFY THE SAME OPERATING FREQUENCY MODE, CHANNEL, AND WIDTH AS THE ACCESS POINT NETWORK YOU JUST SET UP

Change Access Point mode to 802.11s

Specify a Mesh Id (all mesh devices must use the same Mesh Id).

Set Network to Lan.

Wireless Security tab - set WPA3-PSK and specify a Key (aka password) (all mesh devices must use the same Key).

Save (We will do these same steps again to add a mesh network to the 2.4GHz radio1 device).

======== 2.4GHz 802.11s Mesh ========

Add a wifi interface to the radio1 AX/B/G/N device.

Specify a mode, channel, and width.

Change the Access Point mode to 802.11s

Specify a Mesh Id (all mesh devices must use the same Mesh Id).

Set Network to Lan.

Wireless Security tab - set WPA3-PSK and specify a Key (aka password) (all mesh devices must use the same Key).

Save

======== Set Hostname ========

I recommend you go to System - System from the top menu and change the Hostname to whatever you want to name this radio.

Save

======== Set Spamcaster's IP Address ========

Go to Network - Interfaces from the top menu.

Edit the lan interface.

Each Spamcaster must have a unique IPv4 address. Coordinate this amongst your group.

Recommend 192.168.x.1 where x is a different number for each Spamcaster.

IPv4 netmask is 255.255.0.0

If you have a spamcaster or other mesh device connected to internet, you can specify it's IPv4 address in the IPv4 gateway.

======== Applying Changes ========

Click Unsaved Changes in top right, and Save & Apply.

If you've changed the IPv4 address, I recommend you "Apply with revert after connectivity loss".

You will have 90 seconds to connect to the AXT1800 and load the LuCI webpage at:

http://[your_new_IPv4_address]:8080/cgi-bin/luci

Uplug the ethernet cable, wait a few tens of seconds for the AXT1800 to reboot, and reconnect it to obtain a new IP address.

Then you should be able to open the LuCI webpage.

You will have to log back in.

Check the Network - Wireless page and make sure all networks and radios are operational.

If any say disabled, it may be necessary to reboot the device (or edit a setting such as the ESSID or Mesh Id and Save & Apply again).

# Assembly
Remove the silicone molle attachment straps from the generic phone mount by pulling/wiggling.

Remove the silicone phone retaining straps from the generic phone mount by pulling/wiggling (TAKE NOTE OF HOW THESE ARE ARRANGED FIRST).

Take apart the AXT-1800. Save the two mounting screws. Disconnect the antenna cables from the u.fl connector on the board.

Unscrew and remove the plastic cover on the heatsink fins.

Optional: Unplug and unscrew the fan.

Insert the 90 degree power cable into the AXT-1800.

Temporarily install the AXT-1800 into the Spamcaster and mark where the USB cable needs to be cut to properly mate up with the DC power socket.

Uninstall the board and remove the USB C cable.

Cut the USB C cable where marked, then solder the 5V and ground wires to the DC socket, and the other half of the USB cable to the barrel plug. I prefer center pin as 5V but it is your choice.

Remove the molle attachment straps from the generic phone mount, and install them into the Spamcaster.

Optional: fill the Molle Seal's groove with silicone (let it dry) and install them inside the Spamcaster. The Molle Seals are not mandatory.

Install the SMA pigtails onto the AXT-1800.

Plug in the constructed USB C power cable with DC socket.

Install the AXT-1800 using the original board's screws. These are made of the mysterious Chinese cheese metal and are easy to deform/strip. Predrill the hole with a 2mm drill if necessary.

Install the SMA and DC power fittings into their external openings. Optionally seal with silicone.

Install M3 heat set inserts into the main case body where the Cover bolts on.

Optional: fill the Cover's groove with silicone (let it dry).

Install the Cover with M3 bolts.

Install the Latch with a 35mm M3 bolt and lock nut.

Install the Phone Holder with a 50mm M3 bolt and lock nut.

Install the silicone phone retaining straps by forcing them into the Phone Holder slots.

Attach your coaxial cable and antennas.

Power on by plugging in the DC barrel jack and connecting a USB battery pack.

# Licensing
These files are free for personal use. If you wish to sell these models, please reach out to me for a licensing agreement. Modifications are welcome and encouraged, but files must be made freely available. Pull requests with new versions of a design are encourages so that all variants are available at this repository. If your modified version adds additional features or capabilities and you wish to offer it for sale, please reach out (I will likely agree that you should be able to freely sell your modified design if there are sufficient changes).
