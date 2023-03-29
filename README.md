# Window Processes and Windows:
Electron handles processes and windows, such as:

* Main process (server/main terminal);
* Rendered processes as a child of main's one;
* Parent and Child windows;

MacOS systems have a little bit more code on the BrowserWindow instance to make it work properly. An example of a piece of specific MacOS needed code is:

``if (process.platform === 'darwin') {``

  ``app.dock.hide();``

``}``

[Main and Renderer Process](mainAndRendererProcess/main.js)

# To render:

  ``const { BrowserWindow } = require('electron');``

  ``const win = new BrowserWindow({ show: false });``

  ``win.loadURL('https://staging.apmhelp.co/');``

  ``win.once('ready-to-show', () => { win.show() });``


# Browser Window

Doc: https://www.electronjs.org/docs/latest/api/browser-window

[Browser Window Subproject](browserWindow/main.js)

## Iteresting props:
``{center boolean (optional) - Show window in the center of the screen. Default is false.``

``{minWidth Integer (optional) - Window's minimum width. Default is 0.``

``{minHeight} Integer (optional) - Window's minimum height. Default is 0.``

``{maxWidth} Integer (optional) - Window's maximum width. Default is no limit.``

``{maxHeight} Integer (optional) - Window's maximum height. Default is no limit.``

``{alwaysOnTop} boolean (optional) - Whether the window should always stay on top of other windows. Default is false.``

``{fullscreen} boolean (optional) - Whether the window should show in fullscreen. When explicitly set to false the fullscreen button will be hidden or disabled on macOS. Default is false.``

``{preload} string (optional) - Specifies a script that will be loaded before other scripts run in the page. This script will always have access to node APIs no matter whether node integration is turned on or off. The value should be the absolute file path to the script. When node integration is turned off, the preload script can reintroduce Node global symbols back to the global scope. See example here.
  https://www.electronjs.org/docs/latest/api/context-bridge#exposing-node-global-symbols
``

# Electron IPC Error dialog
 - Displays errors between main and rendered processes;
  - It's a modal dialog;
  - It's a child of the main window;
  - It's a child of the main process;

  Here's an example of how to use it:
  [IPC Error Dialog Subproject](ipc/main.js)

# Electron Application Menus
 - It's a menu bar;
 Here's an example of how to use it:
  [Application Menus Subproject](menuDemo/main.js)
  
# Context Menus
  - It's a menu that appears when you right click on a page;
  [Context Shortcuts Subproject](menuDemo/main.js)

# Menu Shortcuts / AppsAccelerators and Global Shortcuts
  - It's a shortcut that you can use to trigger an action;
  Here's an example of how to use it:
  [Menu Shortcuts Subproject](menuDemo/main.js)

# Shell Module
  - It's a module that allows you to access clients' files and folders;
  Here's an example of how to use it:
  [Shell Subproject](shell/index.js)

# Tray Icon
  - It's an icon that appears on the OS taskbar;
  Here's an example of how to use it:
  [Tray Icon Subproject](trayDemo/main.js)

# Electron is able to CRUD files
  - Create, Read, Update and Delete files;
  - It's a module that allows you to access clients' files and folders;

  Here's an example of how to use it:
  [File System Subproject](crudFile/index.js)
