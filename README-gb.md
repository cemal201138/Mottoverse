# 🌟 Mottoverse - Hourly Random Quote Flow (Desktop Widget)

❗ [Turkish README.md file](https://github.com/cemal201138/Mottoverse/blob/main/README.md) ❗

Mottoverse is a modern Python desktop widget application that integrates stylishly and minimally into your Windows desktop, pulling motivational quotes/excerpts from your favorite RSS feeds instantly or hourly.

It is pinned to the desktop layer using native Windows APIs, so it does not disappear when you hide windows (Win + D) and becomes a stylish part of your background.

---

## ✨ Features

* **Pin to Desktop:** Thanks to Windows API integration, the widget stays right above your wallpaper. It can be covered by other windows but is not hidden by the Win + D shortcut.
* **Modern Tokyo Night Theme:** A modern, minimalist interface with a non-eye-straining #1a1b26 and #24283b color palette.
* **Dynamic Resizing:** Automatically adjusts its height according to the length of the content (with wraplength protection). It can also be manually resized using the handles on the top-left and bottom-right.
* **Advanced Windows Features:** Hardware-accelerated window corner rounding (DWM API) on supported Windows versions.
* **Redundant RSS System:** Automatically switches to a backup feed if there is an issue with your primary RSS source.
* **Lockable Interface:** You can lock the widget on the desktop to prevent accidental movement and hide the handles.
* **Smart JSON Configuration:** The URLs you save are automatically stored in the AppData/Roaming/Mottoverse_Data folder of the user, so you don't need to re-enter them each time you open it.

---

## 🛠️ Installation and Execution

### Requirements
The application uses built-in Python libraries (tkinter, urllib, xml, ctypes). Since it contains Windows APIs, it performs best on Windows operating systems. No extra pip install setup is needed.

### Execution
1. Download the latest version of the repository and run the executable file.

2. You can check the [rss-feed](https://github.com/cemal201138/rss-feed) repository for sample RSS sources and structure, or use the example directly.

3. Run the script with Python:
   python main.py

---

## 🚀 User Guide

1. **Initial Setup:** When you start the application for the first time, the RSS Source Settings window will appear. You need to enter at least one valid, verifiable RSS Feed URL here.
2. **Widget Controls:**
   * **Moving:** You can drag the widget to any place on your desktop by holding down anywhere on it.
   * **Resizing:** You can change the widget size using the ◤ and ◢ symbols in the corners.
3. **Right-Click Menu:** You can access the following settings by right-clicking on the widget:
   * 📌 Pin / 🔓 Unlock: Prevents the widget from being moved or resized, fixing its position on the screen.
   * ⚙️ URL Settings: Reopens the settings window to update or change RSS feed links.
   * ❌ Close: Safely closes the application.

---

## 🎨 Screenshots

<img width="474" height="444" alt="Screenshot 2026-06-25 120429" src="https://github.com/user-attachments/assets/8402188a-1c91-428f-845c-9b3e3adc6092" />
<img width="472" height="440" alt="Screenshot 2026-06-25 120406" src="https://github.com/user-attachments/assets/9061bbf7-0194-4e58-98c9-443ead5bd0e4" />
<img width="291" height="177" alt="Screenshot 2026-06-25 120254" src="https://github.com/user-attachments/assets/d6eace68-7af3-480e-876b-c0526f069342" />
<img width="297" height="176" alt="Screenshot 2026-06-25 120451" src="https://github.com/user-attachments/assets/d06a1d9f-fa9a-4377-98b2-b7e39f929b6c" />
<img width="293" height="180" alt="Screenshot 2026-06-25 120652" src="https://github.com/user-attachments/assets/98fcad29-c873-4a2a-ab67-6096bcef9dc8" />

---

## 📝 License

This project is licensed under the MIT license. You are free to develop, fork, and use it in your own projects.
