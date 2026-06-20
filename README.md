ClokoWe M8 Projector Flipper Zero IR Remote

Custom IR remote files for the ClokoWe M8 projector, reverse engineered via brute force IR hunting on a Flipper Zero running Momentum firmware. All 256 possible commands on the device address (08 16) were systematically tested to identify each button's function.


FILES

ClokoWe_M8_Final.ir - IR signal file containing all confirmed button commands
ClokoWe_M8_Remote.txt - Layout file for the Flipper Zero IR Remote app


IR SIGNAL MAP

All signals use protocol NECext with device address 08 16 00 00.

POWER    | 87 78 | Toggles on and off
MUTE     | 58 A7 |
VOL+     | 89 76 |
VOL-     | B5 4A |
Up       | BB 44 | Navigation
Down     | 8D 72 | Navigation
Right    | 8E 71 | Navigation
OK       | B2 4D | Confirm/Select
Menu     | 86 79 | Opens main menu
Settings | 8A 75 | Opens picture/display settings (S button)
Source   | 08 F7 | Input source selection

Note: Left and Back buttons were not found via IR brute force. Left is mapped to Menu as a workaround. Back does not appear to have an IR command on this projector.


BUTTON LAYOUT (IR Remote App)

Up      Tap: Nav Up       Hold: VOL+
Down    Tap: Nav Down     Hold: VOL-
Left    Tap: Menu         Hold: Mute
Right   Tap: Nav Right    Hold: Source
OK      Tap: Confirm      Hold: Power
Back    Tap: Menu         Hold: Exit App


INSTALLATION

Step 1: Copy the IR signal file
Place ClokoWe_M8_Final.ir in:
SD Card/infrared/

Step 2: Copy the remote layout file
Place ClokoWe_M8_Remote.txt in:
SD Card/infrared/remote/
If the remote folder doesn't exist, create it.

Step 3: Access via IR Remote app
The remote will appear inside the IR Remote app on your Flipper under Apps.


ADDING IR REMOTE TO THE FLIPPER MAIN MENU (MOMENTUM FIRMWARE)

To make the IR Remote app accessible directly from the main menu alongside NFC, Infrared, Sub-GHz, etc.:

1. On your Flipper, navigate to Settings
2. Go to Momentum > Interface > Mainmenu
3. Select Add Item
4. Find and select IR Remote from the app list
5. It will now appear in your main menu for quick access


HOW IT WAS MADE

These IR codes were discovered through systematic testing of all 256 possible commands (00 through FF) on device address 08 16 00 00 using the NECext protocol on a Flipper Zero running Momentum firmware (mntm-012).

The device address was first identified by running the Flipper's built-in Universal Projector remote and narrowing down which signal triggered a response (~22% through the universal remote file), then confirmed by testing against the projector directly.

No original remote was available during this process.


CONTRIBUTING

If you find additional button codes (especially Left navigation or Back), please open a PR or issue!
