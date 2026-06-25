# 🌟 MOTTOVERSE - FREQUENTLY ASKED QUESTIONS AND ANSWERS (FAQ) 🌟

---

## 1. INSTALLATION, DEPENDENCIES, AND RUNNING

### Question: Do I need to install any extra Python libraries to run the application?
**Answer:** No. Mottoverse entirely uses Python's built-in libraries (`tkinter`, `urllib`, `xml`, `ctypes`, `json`, `shutil`). This allows it to run out of the box without needing to execute any "pip install" commands.

### Question: When I launch the Python script, the window suddenly closes or doesn't appear on the screen. Why?
**Answer:** If you are running the application for the first time or do not have a valid saved setting, the application hides the main widget window and opens the "Data Source Settings" window in the center of the screen. If you close this window, the application terminates completely. Once you configure the settings and save them, the widget will become visible.

### Question: Is there a pre-compiled .exe version of the application available?
**Answer:** Yes, a compiled `.exe` version is available in the main folder of the project. On Windows computers where Python is not installed, you can use the widget by directly running this `.exe` file.

---

## 2. WINDOWS INTEGRATION AND SYSTEM FEATURES

### Question: Why doesn't this widget disappear when I use the "Show Desktop" (Win + D) shortcut?
**Answer:** The application utilizes native Windows `user32` and `ctypes` APIs. When the widget opens, it attaches as a child window to the background windows managing the Windows desktop layer (`Progman` or `WorkerW`). Thus, the system treats the widget as part of the wallpaper and does not hide it.

### Question: The corners of the window are oval and rounded, just like in Windows 11. Tkinter does not normally support this; how did you achieve it?
**Answer:** The Windows Desktop Window Manager (DWM) API is directly accessed within the code. Hardware-accelerated window corner rounding is enabled by calling the `dwmapi.DwmSetWindowAttribute` function.

### Question: Does this application run on Linux or macOS operating systems?
**Answer:** No. The desktop pinning and advanced interface features of the application depend entirely on native Windows APIs, so it works exclusively on Windows operating systems.

---

## 3. DATA SOURCES AND SYNCHRONIZATION (RSS & JSON)

### Question: What is the difference between RSS mode and Local JSON mode?
**Answer:** **RSS Mode** listens to the live web feeds you specify and automatically updates when a new quote is added. **Local JSON Mode**, on the other hand, takes a local `.json` file on your computer as a reference and provides a continuous stream by making random selections within the second interval you define.

### Question: Can I adjust how often quotes change in RSS mode?
**Answer:** No, the seconds adjustment on the interface applies only to JSON mode. RSS mode monitors live updates (new quotes) from the source in the background at fixed 2-second intervals and updates only when a new quote is published.

### Question: Does the local JSON file I select by clicking "Browse" get deleted from its original location?
**Answer:** No. The file you select is safely copied to the application's data area (`%appdata%/Mottoverse_Data/mottoverse.json`), and the application references this copied file while running. Your original file remains untouched.

---

## 4. USER EXPERIENCE AND INTERFACE CONTROLS

### Question: Is it possible to lock the position of the widget and prevent it from being moved accidentally?
**Answer:** Yes. When you right-click anywhere on the widget and select the "**📌 Pin**" option, the interface locks. Once locked, the resizing handles (`◤` and `◢`) in the corners are hidden, and the widget cannot be dragged or resized. To move it again, simply right-click and select "**🔓 Unlock**".

### Question: Why don't the texts overflow or get clipped when I resize the window with the mouse?
**Answer:** The application features a dynamic text wrapping (`wraplength`) architecture. As you change the width, the line-wrap limit of the text updates automatically, and the window height dynamically expands based on the length of the content.

---

## 5. ERROR HANDLING AND TROUBLESHOOTING

### Question: I get a "Primary URL did not return a valid RSS feed" error when adding an RSS address. What does it mean?
**Answer:** For the application to validate the connection, the entered link must be in a standard XML format and contain at least one `<item>` or `<entry>` tag, along with `<title>`, `<description>`, and `<author>` structures.

### Question: Does the widget close if my internet connection drops or if the website I get the RSS from crashes?
**Answer:** No. The code architecture includes redundant RSS and protected error blocks (`try-except`). If the primary address is unreachable, it automatically switches to the backup address you defined. If none are reachable, the application does not crash; it safely waits in the background and resumes fetching the stream once the internet connection is restored.
