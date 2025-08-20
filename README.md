# Windows Script Files → Edit with Visual Studio Code

By default, Windows 10/11 opens `.bat`, `.cmd`, `.ps1`, and `.vbs` files in **Notepad** (or PowerShell ISE for `.ps1`) when you right-click and choose **Edit**.  
This registry tweak changes that behavior so they will open in **Visual Studio Code** instead.

---

## ⚠️ Disclaimer
- This will modify the Windows Registry.  
- Use at your own risk (safe, but always good practice to back up).  
- Only tested on **Windows 10 Only**.  

---

## How to Use
1. Download [`edit_scripts_vscode.reg`](./edit_scripts_vscode.reg).  
2. Double-click the file.  
3. Accept the warning when Windows asks to add the registry key.  
4. Done ✅  

Now when you **Right-click → Edit** on:
- `.bat`
- `.cmd`
- `.ps1`
- `.vbs`

They will all open directly in **Visual Studio Code** instead of Notepad.


# Uninstall / Revert

If you want to revert back to default (Notepad / ISE):

Open Registry Editor (Win + R, type regedit).

Navigate to the same keys.

Change the value back to Notepad or delete the custom entry.

Default value for .bat for example is: @="notepad.exe %1"

---

## Example Registry Entry
```reg
[HKEY_CLASSES_ROOT\batfile\shell\edit\command]
@="\"C:\\Users\\<Userdevicename>\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" \"%1\""
