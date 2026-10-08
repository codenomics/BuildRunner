# BuildRunner

> This application is built by AI. I made this for myself and I'm uploading it to GitHub for backup and to share in case anyone can get any use out of it. It's pretty specific to my setup and my needs, but if you can get any use out of it, then enjoy.
>
> Use at your own risk. I offer no warranty or guarantees for this software.

## Download

**Latest version: v1.11** (Oct 8, 2026)

- [BuildRunner_v1.11_no-install.zip](https://github.com/codenomics/BuildRunner/releases/download/v1.11/BuildRunner_v1.11_no-install.zip) - 137 KB
- [BuildRunner_v1.11_Setup.exe](https://github.com/codenomics/BuildRunner/releases/download/v1.11/BuildRunner_v1.11_Setup.exe) - 205 KB
- [BuildRunner_v1.11_source.zip](https://github.com/codenomics/BuildRunner/releases/download/v1.11/BuildRunner_v1.11_source.zip) - 127 KB

What's new in v1.11:

- updater versioning fix**

Older versions are on the [Releases page](https://github.com/codenomics/BuildRunner/releases).

## Getting started

### Installer (recommended)

1. Download the file ending in `_Setup.exe` above.
2. Double-click it and click Install. It installs just for you - no admin password needed - and adds Start menu and Desktop shortcuts.
3. To remove it later: Windows Settings > Apps, find BuildRunner and click Uninstall.

### No install (portable zip)

1. Download the file ending in `_no-install.zip` above.
2. Right-click it > Extract All, and pick a folder. Don't run it from inside the zip.
3. Open the folder and double-click the app's .exe. Nothing is installed; delete the folder to remove it.

Windows says "Windows protected your PC"? Click More info > Run anyway. It shows that for apps without a paid signing certificate.

## Source code

Want to see how it works, or build it yourself? Download the file ending in `_source.zip` above, extract it and double-click `Build.bat`. It only uses the C# compiler that already comes with Windows, so there is nothing to install.

## More details

```
BUILDRUNNER
===========

Keeps a folder full of small apps tidy, and makes zips of them you can share.


GETTING STARTED
---------------
Pick one. Both give you the same app.

OPTION 1 - INSTALLER (recommended)
  Download the file ending in _Setup.exe, double-click it and click Install.
  It installs just for you (no admin password) and adds Start menu and
  Desktop shortcuts. Needs Windows 10 or 11 (64-bit).
  To remove it later: Windows Settings > Apps > BuildRunner > Uninstall.

OPTION 2 - NO INSTALL (zip)
  1. Download the file ending in _no-install.zip. Right-click it -> Extract
  All... and put the BuildRunner folder somewhere it can stay (for example
  Documents). Don't run it from inside the zip.
  2. Double-click BuildRunner.exe. Nothing is installed; to remove it,
  delete the folder.

EITHER WAY
  BuildRunner looks for your apps in the folder you pick. Click Change... at
  the top and choose the folder that holds your app projects (one folder per
  app). If you put the BuildRunner folder inside that folder, it finds your
  apps by itself.

"Windows protected your PC"? Click "More info" -> "Run anyway".
Windows shows that for apps downloaded from the internet that aren't
signed with a paid certificate.


USING IT
--------
Your apps are listed on the left, with "All apps" at the top.
Pick one, then use the three tabs:

CLEAN
- Lists files you don't need: build logs, old backups, preview pictures,
  temp files. Ticked ones go when you click Clean.
- App logs are listed too, but not ticked. Tick them if you want them gone.
- Everything goes to the Recycle Bin, so you can always get it back.

ORGANIZE
- Rename or move an app's folder, open it, or run its Build.bat.

SHARE
- Every file in the app gets a tag. Click a tag to change it:
    In zip   = needed to run the app
    Readme   = becomes "READ ME FIRST.txt" in the zip
    Left out = not in the zip
- Type a version (1.0, 1.1 ...) and what changed, one change per line.
- Make zip saves it as  Releases\<App>\<App>_v1.0.zip  in your main folder,
  adds a WHAT'S NEW.txt listing every version, and keeps a history in
  Releases\<App>\versions.txt.
- Stream Deck plugins get a one-click installer instead of a zip, a new one
  for every version: a .streamDeckPlugin file for Elgato Stream Deck, and a
  Setup .exe for VSD Craft (it closes VSD Craft, puts the plugin in and
  opens it again; running it again updates or uninstalls the plugin).
  A zip holding the installer, WHAT'S NEW.txt and the readme is made too.
- If an app's Releases folder has a next-release.txt (a line
  "version = 1.1" and then one change per line), the Share tab fills in
  the version and notes from it.
- Before zipping, BuildRunner warns about things you may not want to share,
  like paths to your Windows user folder.


INSTALLERS (normal apps)
- The button under the file list picks Zip, Installer, Zip + installer, or
  Zip + installer + code for each app. An installer is one Setup.exe that installs just for you
  (no admin question) with Start menu and Desktop shortcuts and an entry
  in Windows' Apps list for uninstalling. No source code inside.
- To put your name on installers, add a line  publisher = Your Name
  under [settings] in BuildRunner-rules.txt.


SHARING YOUR CODE (optional)
- Zip + installer + code also makes  <App>_v1.0_source.zip : a cleaned COPY of
  the app's code (your own files are never changed). It holds the code files
  Build.bat compiles, Build.bat, icons and pictures, and a README.txt that
  says how to build it. People extract it and double-click Build.bat.
- In the copy, comments that name an AI are fixed or dropped. To take a
  private name out of your comments too, add a line  scrub = Name  under
  [settings] in BuildRunner-rules.txt (Name's becomes "my", Name becomes
  "the user").
- The finished code zip is then checked like an upload: paths to your
  Windows user folder, tokens, keys, email addresses, this PC's name, an AI's
  name, or a scrub name still in the code itself. If anything is found the
  code zip is not kept and you get a list of what and where.
- For Windows apps only (not Stream Deck plugins).


GITHUB (optional)
- Click "Connect GitHub" at the top and follow the window: you make your
  own token (tick only "repo") and paste it in. It stays on your PC,
  scrambled for your Windows account. Nothing about anyone else's account
  is built in.
- On an app's Share tab: "Create GitHub repo" makes a public repo with a
  short README, or "Link existing repo" uses one you have. Nothing is
  ever created by itself.
- Linked apps get "Make and upload": makes the zip / installer and posts
  it as a GitHub release with your notes, and updates the README.
- BuildRunner only uploads the finished zip / installer, the cleaned code
  zip (only if you chose Zip + installer + code) and the README. It stops,
  and tells you why, if a file looks like a log, a key, a password-like
  token, an email address, a path to your Windows user folder, or code
  that wasn't made by BuildRunner.


THE RULES FILE
--------------
BuildRunner-rules.txt in your main folder says what counts as junk and
what goes in each app's zip. "Edit rules" opens it in Notepad; BuildRunner
notices changes by itself.


GOOD TO KNOW
------------
- Updates: a few seconds after it starts, BuildRunner quietly checks GitHub for a
  newer version. If there is one, the "Updates" button at the top right changes
  to "Update available" - click it to update. Click "Updates" any time to check
  now; that box also turns the startup check on or off.
- F5 = refresh. The lists also refresh when you come back to the window.
- Settings are kept in %APPDATA%\BuildRunner\settings.txt.
- If something goes wrong, BuildRunner-log.txt next to BuildRunner.exe says what.
- To remove BuildRunner: delete its folder, plus %APPDATA%\BuildRunner.
```

