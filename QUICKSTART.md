# QUICK START GUIDE

## For Absolute Beginners

### Step 1: Open the Project in Android Studio

1. **Launch Android Studio**
2. Click **"Open"** (or File → Open if Android Studio is already open)
3. Navigate to this **ChoresApp** folder
4. Click **"OK"**

### Step 2: Wait for Gradle Sync

- Android Studio will automatically start syncing
- You'll see a progress bar at the bottom
- This can take 2-10 minutes on first load
- Just wait until it says "Gradle sync finished"

### Step 3: Connect Your Device OR Start Emulator

**Option A - Use Your Phone:**
1. Enable "Developer Options" on your Android phone
2. Enable "USB Debugging" in Developer Options
3. Connect phone via USB cable
4. Allow USB debugging when prompted on phone

**Option B - Use Emulator:**
1. In Android Studio, click the device dropdown (top toolbar)
2. Click "Device Manager"
3. Click "Create Device"
4. Choose a device (Pixel 5 recommended)
5. Choose a system image (R or higher recommended)
6. Click "Finish"
7. Click the Play button next to your new emulator

### Step 4: Build and Run

1. Click the **green "Run" button** (▶️) in the toolbar
   - OR press **Shift + F10**
2. Wait for the build to complete
3. The app will automatically install and launch!

---

## Building the APK File (To Share)

### Debug APK (Quick and Easy)

1. Go to **Build** → **Build Bundle(s) / APK(s)** → **Build APK(s)**
2. Wait for build to complete
3. Click **"locate"** in the notification popup
4. Your APK is there! (app-debug.apk)

### Install APK on Phone

1. Copy the APK file to your phone
2. Open the APK file on your phone
3. Allow "Install from unknown sources" if prompted
4. Click "Install"

---

## Troubleshooting

**"Gradle sync failed"**
- Go to File → Invalidate Caches / Restart → Invalidate and Restart

**"SDK not found"**
- Go to File → Project Structure → SDK Location
- Click the download icon to install Android SDK

**"Build failed"**
- Open SDK Manager (Tools → SDK Manager)
- Install "Android 14.0 (API 34)"
- Click "Apply" and wait for install

**App crashes on launch**
- Check your phone is Android 7.0 or higher
- Try Build → Clean Project, then Build → Rebuild Project

---

## What You Get

✅ A native Android app with your chores HTML tracker
✅ Works offline after installation
✅ Data saved locally on device
✅ Can be shared as APK file
✅ Professional app icon and branding

---

## Next Steps

- **Customize app name**: Edit `app/src/main/res/values/strings.xml`
- **Change app icon**: Replace `app/src/main/res/drawable/ic_launcher.xml`
- **Update HTML**: Edit `app/src/main/assets/index.html`

After making changes, click the green Run button again to see them!
