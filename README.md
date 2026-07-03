# 3D Transparent Desktop Mascot Pet 🐰

A floating, borderless, fully transparent (RGBA 0,0,0,0) 3D interactive companion pet application for Windows, powered by **Electron** and **Three.js (WebGL)**.

The mascot floats on top of your working windows, bobbing gently. It captures clicks and drags when hovered directly, and passes clicks straight through to the applications underneath when clicking in transparent areas.

---

## 🚀 How to Run the App

### Option A: Standalone Executable (No Setup Required)
Perfect for instant use without running terminal commands.

1. Open **File Explorer** and navigate to:
   [DesktopPet-win32-x64](file:///C:/Users/space/.gemini/antigravity-ide/scratch/desktop-pet/DesktopPet-win32-x64)
2. Double-click **`DesktopPet.exe`** to start your pet mascot.

> [!TIP]
> Right-click `DesktopPet.exe` ➔ *Send to* ➔ *Desktop (create shortcut)* to launch it directly from your desktop.

---

### Option B: Local Node.js Development
Ideal if you want to inspect, debug, or extend the JavaScript source files.

1. Ensure [Node.js](https://nodejs.org) is installed.
2. Open terminal and navigate to the project directory:
   ```bash
   cd C:\Users\space\.gemini\antigravity-ide\scratch\desktop-pet
   ```
3. Start the dev app:
   ```bash
   npm start
   ```
4. Recompile the production executable after modifying code:
   ```bash
   npm run build
   ```

---

## 🕹️ Controls & Interaction Guide

| Mouse Action | Target | Description |
| :--- | :--- | :--- |
| **Hover** | Over character | Cursor changes to a pointer, enabling interaction. |
| **Left Click** | On character | Plays a squash-and-stretch windup, a high jump, and a 360° spin animation. |
| **Left Click + Drag** | On character | Smoothly repositions the mascot anywhere on your monitor(s). |
| **Click** | Outside character | Passed through to the folders, IDE, or browser behind the window. |
| **Hover ➔ Click ⚙️** | Top-right corner | Opens the glassmorphic Settings Panel (if enabled). |

---

## 💡 Customize with Your Own 3D Models (Zero-Code Customization)

The app automatically detects, centers, and displays any 3D asset you drop in:

1. Locate the **`assets/`** folder:
   - Development path: [assets/](file:///C:/Users/space/.gemini/antigravity-ide/scratch/desktop-pet/assets)
   - Executable path: [DesktopPet-win32-x64/assets/](file:///C:/Users/space/.gemini/antigravity-ide/scratch/desktop-pet/DesktopPet-win32-x64/assets)
2. Drop any **`.glb`** or **`.gltf`** model file (e.g. your favorite Pokémon) into this directory.
3. Launch the app. The engine will:
   - **Scan** and read your 3D asset.
   - **Auto-center and load** the geometry at its original modeled size `(scale: 1, 1, 1)`.
   - **Auto-fit viewport:** If settings are disabled, the window automatically resizes and the camera repositions itself so the model fits the window perfectly.
   - **Auto-play** the first embedded skeletal animation track (e.g., Idle/Walk).
4. **Fallback:** If you empty the `assets/` folder, the application immediately falls back to rendering the default pink bunny mascot.

---

## ⚙️ Interactive Settings Panel

You can enable an overlay settings panel by adding a configuration file:

1. **How to Enable:** Place a text file named **`settings`** (or `settings.txt`) in your `assets/` folder.
2. **Accessing the Panel:** Hover your mouse cursor over the mascot. A gear icon `⚙️` will appear in the top-right corner. Click it to open the Settings Panel.
3. **Editable Settings:**
   - **Window Width & Height:** Adjust the window dimensions from a minimal **30px** up to your **full computer screen size**.
   - **Model Scale:** Manually zoom/scale the 3D character from **0.1x** to **5.0x**.
   - **Enable Idle Bobbing:** Checkbox to toggle the slow floating vertical idle animation on or off.
4. **Resizing Sync & Revert Rules:**
   - Sliders update only their numerical text labels in real-time while dragging.
   - Changes are applied to the window and model **only when you click "Save Settings"**.
   - Clicking **"Close"** cancels changes and reverts sliders back to the last saved parameters.

---

> [!NOTE]
> To modify the source scripts, open the project inside your editor and make changes directly in [renderer.js](file:///C:/Users/space/.gemini/antigravity-ide/scratch/desktop-pet/renderer.js) or [main.js](file:///C:/Users/space/.gemini/antigravity-ide/scratch/desktop-pet/main.js).
