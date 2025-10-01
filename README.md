# androidtvbox

# Install Waydroid on Ubuntu
1. Install curl and certificates
```
sudo apt install curl ca-certificates -y
```

3. Add the official Waydroid repository
```
curl https://repo.waydro.id | sudo bash
```

5. Update your package list and install Waydroid
```
sudo apt update && sudo apt install waydroid -y
```

# Download Android TV Build
GitHub link: https://github.com/supechicken/waydroid-androidtv-build

# Import Android TV Build into Waydroid
1. Clean up old Waydroid data (if needed)
```
waydroid session stop
sudo rm -rf ~/.local/share/waydroid
sudo rm -rf /var/lib/waydroid/overlay*
```

2. Copy the Android TV images
```
sudo mkdir -p /etc/waydroid-extra/images/
sudo cp ~/Downloads/system.img /etc/waydroid-extra/images/system.img
sudo cp ~/Downloads/vendor.img /etc/waydroid-extra/images/vendor.img
```

3. Re-initialize Waydroid with the Android TV images
```
sudo waydroid init -f
```

# Register Android TV on Google’s Uncertified Device Website
1. Get your Android ID
```
sudo waydroid shell -- sh -c "sqlite3 /data/data/*/*/gservices.db 'select * from main where
name = \"android_id\";'"
```

2. Register your device here:
https://www.google.com/android/uncertified
