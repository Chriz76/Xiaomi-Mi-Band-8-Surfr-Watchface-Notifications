# Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications

Display the height of the last jump, maximum jump height of our session and number of jumps on your Xiaomi Mi Band 8. Based on the data measured on your android phone by the surfr app. Vibrate the band on every jump.

<img src="https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/assets/48691511/5381f8fb-cd3b-446e-83bf-4c552832b196" width="200"/>
<img src="https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/assets/48691511/c54e208a-3d89-4ddd-a3cd-0ba4d73ec89c" width="200"/>

This tutorial is only working with the Xiaomi MI Band 8. Not with the Xiaomi Mi Band 8 Active or other Smartbands. However it should be possible to use other bands. For the watches supported by https://github.com/m0tral/EasyFace it should be simple. Just ask me in the issues. It is also possible to customize the watch face.

## There are some apps and tools involved
- The Mi Band 8 is setup with the official Mi Fitness app to receive the auth key: https://play.google.com/store/apps/details?id=com.xiaomi.wearable&hl=de&gl=US
- The Band uses a special watchface to display the jump data: https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/blob/main/watch-face.zip
- The watchface is installed via the app "Mi Band 8 Watch Faces" on the Band: https://play.google.com/store/apps/details?id=asn.ark.miband8&hl=de&gl=US&pli=1
- The surfr app runs in wetsuit mode and automatically creates an android broadcast on every jump: https://play.google.com/store/apps/details?id=com.kiter&hl=de&gl=US
- The Automate app intercepts surfr's broadcasts, converts them to a special format, increases the jump count, the max jump height and sends all data to the gadgetbridge app and also tells gadgetbridge to vibrate the band: https://play.google.com/store/apps/details?id=com.llamalab.automate&hl=de&gl=US
- Automate uses the two flows:
  - https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/blob/main/Vibrate.flo
  - https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/blob/main/Surfr%20check.flo
- Gadgetbridge is connected to the Mi Band 8 and sends the jump data to the Band and tells it to vibrate: https://freeyourgadget.codeberg.page/fdroid/repo/nodomain.freeyourgadget.gadgetbridge.nightly_nopebble_0.80.0-9ba96231c.apk
- The Band vibrates and displays the jump data

## Howto make it work

Warning: This may break your Band. So do it on your own risk.

- Install the Mi Fitness app, setup your band and connect it to the Mi Fitness app.
- Install gadgetbridge. You have to use one of the latest nightly builds (see the link above) because only those builds contain the necesarry interfaces.  
- Shutdown the Mi Fitness app and connect your Band to Gadgetbridge following this guide: https://gadgetbridge.org/basics/pairing/huami-xiaomi-server/
- Test in the gadgetbrige debug menu that you can make the band vibrate.
- Allow Debug Commands in the Intent Api gagetbridge settings.
- Install the Automate app.
- Download the two Automate flows and import them to Automate.
- Start the vibrate flow in Automate. Your Band should vibrate.
- Edit the Surf Check flow in Automate to link the vibrate call to the vibrate flow.
- Start the Surf Check flow.
- Start the surfr app in wetsuite mode.
- Simulate a jump by bringing your phone down to the ground, then shaking it a bit left and right and fast pull your arm up and then slowly down.
- You might have to try it several times but then the surfr app should detect a jump and display a notification.
- Switch to Automate and you should see in the log of the Surf Check flow that it detected the notification.
- Install the "Mi Band 8 Watch Faces" app.
- Download the watch-face.zip and use the "Mi Band 8 Watch Faces" app to install it on the band.
- Reconnect gadgetbridge to your Band.
- Simulate another jump. The data should now be displayed on your band.
