# Fix magenta/purple screen 

The following repository is for archiving the script for fixing magenta/purple screen on macOS. 
Please note that I do not own any part of the script. This is simply an upload as the main reddit post was flagged as spam. 

I'll leave the original link to pay respects: [Press F to pay respects](https://www.reddit.com/r/hackintosh/comments/atxnev/fixing_purplemagenta_screen_on_a_macoshackintosh/)

# Requirements

- Connected display with magenta/purple screen issue
- Basic BASH navigation knowledge
- Disabled SIP 

# Usage

## Step 1: check SIP status

First of all you need to check if your SIP is disabled or not. To do this, open a terminal window and type:

`csrutil status`

If the output is like:

`System Integrity Protection status: disabled.`

then you can proceed to the next step.

## Step 2: patch-edid.rb
From a terminal window type: 

`./patch-edid.rb`

It will output a folder called `DisplayVendorID-XXXX/`.

Then copy the folder into:

- `/System/Library/Displays/Contents/Resources/Overrides` 
- `/System/Library/Displays/Overrides` for < El Capitan

by using:

`sudo su` for getting elevated privileges

then copy the folder to:


`cp -R DisplayVendorID-XXXX /System/Library/Displays/Contents/Resources/Overrides`

or 

`cp -R DisplayVendorID-XXXX /System/Library/Displays/Overrides` if on < El Capitan

Finally reboot and you should have fixed monitor colours :)

## Credits

* **Apple** for macOS
* **von Andreas S.** for forum thread on [embdev.net](https://embdev.net/topic/284710)



