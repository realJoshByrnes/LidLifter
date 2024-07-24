# LidLifter - Prevent your MacBook from going to sleep when on AC.

LidLifter is a macOS LaunchDaemon crafted to keep your MacBook awake when in Clamshell mode, particularly when connected to AC power.
It prevents your MacBook from sleeping with the lid closed, ensuring uninterrupted workflows for developers, presenters, and users of external displays.

Beyond MacBooks, LidLifter extends its utility to any macOS device connected to AC power, allowing users to maintain continuous operation even when the lid is closed.
Whether you're presenting slides, running lengthy computations, or managing servers remotely, LidLifter provides the reliability you need.


## Installation

### Installing LidLifter

To install LidLifter onto your macOS system:

1. **Open Terminal.**

2. **Download the `.plist` File:**
   - Use `curl` to download `au.byrnes.jd.lidlifter.plist` from GitHub:
     ```bash
     sudo curl -o /Library/LaunchDaemons/au.byrnes.jd.lidlifter.plist \
       https://raw.githubusercontent.com/realJoshByrnes/lidlifter/main/au.byrnes.jd.lidlifter.plist
     ```

3. **Load the LaunchDaemon:**
   - Start LidLifter to prevent macOS from sleeping in Clamshell mode:
     ```bash
     sudo launchctl load -w /Library/LaunchDaemons/au.byrnes.jd.lidlifter.plist
     ```

### Uninstallation

To uninstall LidLifter from your macOS system:

1. **Open Terminal.**

2. **Unload the LaunchDaemon:**
   - Stop LidLifter from running:
     ```bash
     sudo launchctl unload -w /Library/LaunchDaemons/au.byrnes.jd.lidlifter.plist
     ```

3. **Remove the LaunchDaemon File:**
   - Delete `au.byrnes.jd.lidlifter.plist` from `/Library/LaunchDaemons/`:
     ```bash
     sudo rm /Library/LaunchDaemons/au.byrnes.jd.lidlifter.plist
     ```

## Managing LidLifter on macOS

### Disabling LidLifter

To temporarily disable LidLifter and allow macOS to sleep when connected to AC power:

1. **Open Terminal.**

2. **Unload the LaunchDaemon:**
   - Stop LidLifter from preventing macOS from sleeping.
     ```bash
     sudo launchctl unload -w /Library/LaunchDaemons/au.byrnes.jd.lidlifter.plist
     ````

### Enabling LidLifter

To enable LidLifter again after disabling it:

1. **Open Terminal.**

2. **Load the LaunchDaemon:**
   - Start LidLifter to prevent macOS from sleeping when connected to AC power:
     ```bash
     sudo launchctl load -w /Library/LaunchDaemons/au.byrnes.jd.lidlifter.plist
     ```

### Checking if LidLifter is Running

1. **Open Terminal.**

2. **Check if LidLifter is running:**
   - Check the LaunchDaemon status:
     ```bash
     sudo launchctl print system/au.byrnes.jd.lidlifter | grep 'job state'
     ```