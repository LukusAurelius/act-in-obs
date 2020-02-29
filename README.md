# act-in-obs
### Capturing Advanced Combat Tracker in OBS

Advanced Combat Tracker, or ACT, is used by many FFXIV players to track DPS. The thing is, it's notoriously difficult to capture in OBS. Window capture doesn’t work, and display capture isn’t optimal. After several hours of searching, I had found guides that showed how to capture ACT, but none of them showed how to capture ACT with a custom theme (such as Kagerou). So, I decided to make a guide myself. (FYI, I made this for a friend in 2018 but neglected to post it online until now.)

Here's a screenshot of a friend's OBS with ACT captured: ![ACT working in OBS](https://i.imgur.com/r0FBtTo.png)

You can see ACT in the lower right of the preview. Tutorial time!

1. Get the [latest release of ACTWebSocket](https://github.com/ZCube/ACTWebSocket/releases).
2. Once the .zip is downloaded but BEFORE you unzip it, right click the .zip and click Properties. At the bottom of the properties window, there is a checkbox labelled “Unblock”. Check it and click OK.
3. Extract the .zip somewhere.
4. Open ACT as an administrator. Open the Plugins tab, then Plugin Listing. Click Browse and navigate to the unzipped files, selecting “ACTWebSocket.dll” when you arrive. When you are back at the ACT window, click “Add/Enable Plugin”. If you encounter any errors while enabling the plugin, make sure that ACT is being run as an administrator and right click on each of the unzipped files and unblock them.
5. You should now have a tab titled “ACTWebSocket” in the Plugins folder in ACT. Click on it. You should be presented with a page which looks almost exactly like this: ![ACTWebSocket](https://i.imgur.com/pZAYSXU.png)

6. Under “Host”, set “Host” to “Loopback (127.0.0.1)”. You can leave the port as-is.
7. Go to your OverlayPlugin tab in ACT and copy the URL. Go back to the ACTWebSocket tab; under "Web Skins", click "Add URL" and paste the URL you just copied.
8. Under “Server Status”, click “On”. If presented with any Windows Firewall alerts, just check the boxes for both public and private networks and click OK.
9. Click on the entry you added under "Web Skins" and click "Open URL". Copy the URL in your address bar; this is what you'll be pointing OBS at.
10. Open OBS and create a Browswer Source. Paste the URL into the URL field, and delete everything in the CSS field.
11. Click OK. It should work now. I recommend using the width and height fields in the Browser Source properties to change the size of the overlay.

### Kagerou-specific additional steps:  

Kagerou has tons of settings to customize the look of the overlay, but it shows up as stock when captured in OBS. Good news is, there's a fix.

1. Change the Browser Source URL to `http://kagerou.hibiya.moe/config/index.html`.
2. Under the source list in OBS, right click the Browser Source and click "Interact". You'll be presented with a window in which you can interact with the page. Here, you can edit settings, including importing settings from your main overlay using the Import/Export menu. Ignore the message that says the overlay failed to reload.
3. Change the Browser Source URL back to what you got from ACT. Your overlay should look exactly as you configured it.

## Other stuff

I did the bulk of the work for this guide in 2018, though this version is revised slightly. Please let me know if there are any issues.

If you have problems getting this working, check your firewall settings, make sure you're running ACT as admin, and make sure you unblocked the files for the websocket. If it's still not working, you can post an issue, though my troubleshooting ability is limited as I am not currently subbed to FFXIV (as of 2020.2.28).

You may share this guide and use it as a basis for video tutorials etc, though you must provide attribution. A link to this repo works fine.  
This guide is licensed under Creative Commons Attribution 4.0 International; see LICENSE.txt for more info.

#### Special thanks to:
Amber and Blubs  
