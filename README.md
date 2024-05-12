## Magic Mouse 2 Ubuntu

### Description
This repository contains a Bash script for enabling scroll functionality on the Magic Mouse 2 in Ubuntu. The script utilizes parameters for the hid-magicmouse module to emulate scroll wheel behavior, middle click functionality, and adjust scroll acceleration and speed.

<img src="https://github.com/matiasrodlo/magic-mouse-ubuntu/assets/52969662/db06c8de-5ee5-4ca0-8a79-3ad5887ac5a4" alt="Magic Mouse Gestures">

### Usage
1. **Create the Script:**
   - Create a file named `scroll.sh` and paste the following content:
     ```bash
     #!/bin/bash
     sudo modprobe -r hid-magicmouse
     sudo modprobe hid-magicmouse emulate_scroll_wheel=Y emulate_3button=Y middle_click_3finger=Y scroll_acceleration=Y scroll_speed=12
     ```
   - Ensure the script has executable permissions.

2. **Move the Script:**
   - Move the `scroll.sh` script to the user's root folder `~/` using the `mv` command:
     ```bash
     mv scroll.sh ~/scroll.sh
     ```

3. **Add an Alias to .bashrc:**
   - Open the `.bashrc` file in a text editor (e.g., nano or vim):
     ```bash
     nano ~/.bashrc
     ```
   - Add the following line at the end of the file:
     ```bash
     alias scroll='~/scroll.sh'
     ```
   - Save the changes and exit the text editor.

4. **Execute the Script:**
   - Once the Magic Mouse 2 is connected using bluetooth, open a terminal and type `scroll` to execute the script. This will enable the configured scroll functionality for the device.

### Note
- The script must be executed with `sudo` or as a user with sufficient permissions to load/unload kernel modules.
- Adjust parameters in the script (`emulate_scroll_wheel`, `emulate_3button`, `middle_click_3finger`, `scroll_acceleration`, `scroll_speed`) as needed to customize mouse behavior.
