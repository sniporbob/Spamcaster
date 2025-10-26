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

# Configuration
You'll want to configure the wireless interfaces for 802.11s mesh, and also set up at least one interface as an access point. Detailed instructions to come shortly.
The instructions are more or less the same as setting up the Rocket M5 for mesh operation, except the AXT-1800 was recently reported to already have the necessary packages preinstalled:
https://teamawarenesskit.org/viewtopic.php?t=36
The AXT-1800 has 2 wireless interfaces (2.4GHz and 5GHz) that get set up independently, then bridged.

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
