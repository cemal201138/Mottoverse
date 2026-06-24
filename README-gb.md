# 🌟 Mottoverse - Hourly Random Quote Stream (Desktop Widget)

❗ [Türkçe README.md dosyası](https://github.com/cemal201138/Mottoverse/blob/main/README.md) ❗

Mottoverse is a sleek and minimalist Python desktop widget that seamlessly integrates into your Windows desktop. It fetches motivational quotes and sayings from your favorite RSS feeds instantly or on an hourly basis.

By utilizing native Windows APIs, the widget pins itself directly to the desktop layer. This ensures it stays neatly as a part of your wallpaper background and won't disappear when you hide all windows (Win + D).

---

## ✨ Features

* **Pin to Desktop:** Powered by Windows API integration, the widget sits right above your wallpaper. Other windows can overlay it, but it remains visible even when using the Win + D shortcut.
* **Modern Tokyo Night Theme:** A clean, eye-friendly user interface featuring a modern #1a1b26 and #24283b color palette.
* **Dynamic Auto-Resizing:** Automatically adjusts its height based on the content length (safeguarded with wraplength). It can also be resized manually via the top-left and bottom-right grips.
* **Advanced Windows Styling:** Hardware-accelerated window corner rounding via DWM API on supported Windows versions.
* **Fallback RSS System:** If your primary RSS feed encounters an issue, the widget automatically switches to your secondary backup stream.
* **Lockable Interface:** You can lock the widget on your desktop to prevent accidental moving or resizing, which also hides the resizing grips.
* **Smart JSON Configuration:** Saved URLs are automatically stored in the user's AppData/Roaming/Rss_Soz directory, so you don't have to re-enter them on every launch.

---

## 🛠️ Installation & Usage

### Requirements
The application relies purely on Python's built-in libraries (tkinter, urllib, xml, ctypes). Since it includes native Windows APIs, it is only fully functional on Windows operating systems. No external pip install packages are required.

### Running the App
1. Clone or download this repository to your local machine:
   git clone https://github.com/YOUR_USERNAME/mottoverse.git
   cd mottoverse

2. Run the script using Python:
   python main.py

---

## 🚀 User Guide

1. **Initial Setup:** When you launch the application for the first time, the RSS Feed Settings window will appear. You must enter at least one valid and verifiable RSS Feed URL here.
2. **Widget Controls:**
   * **Moving:** Click and hold anywhere on the widget to drag and reposition it on your desktop.
   * **Resizing:** Use the ◤ and ◢ symbols at the corners to manually change the widget size.
3. **Context Menu (Right-Click):** Right-click anywhere on the widget to access the following settings:
   * 📌 Pin / 🔓 Unlock: Locks the widget's position and size on the screen, hiding the resize grips.
   * ⚙️ URL Settings: Reopens the setup window to update or change your RSS feed links.
   * ❌ Close: Safely exits the application.

---

## 🎨 Screenshots

To be added

---

## 📝 License

This project is licensed under the MIT License. Feel free to develop, fork, and use it in your own projects.
