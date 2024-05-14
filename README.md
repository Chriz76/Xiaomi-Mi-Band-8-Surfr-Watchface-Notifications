# Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications

Display the height of the last jump, maximum jump height of our session and number of jumps on your Xiaomi Mi Band 8. Based on the data measured on your android phone by the surfr app. Vibrate the band on every jump.

<img src="https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/assets/48691511/5381f8fb-cd3b-446e-83bf-4c552832b196" width="200"/>
<img src="https://github.com/Chriz76/Xiaomi-Mi-Band-8-Surfr-Watchface-Notifications/assets/48691511/c54e208a-3d89-4ddd-a3cd-0ba4d73ec89c" width="200"/>

This tutorial is only working with the Xiaomi MI Band 8. Not with the Xiaomi Mi Band 8 Active or other Smartbands. However it should be possible to use other bands. For the watches supported by https://github.com/m0tral/EasyFace it should be simple. Just ask me in the issues.

There are some apps and tools involved:
- The Mi Band 8 has a special watchface installed via the app "Mi Band 8 Watch Faces" to display jump data: https://play.google.com/store/apps/details?id=asn.ark.miband8&hl=de&gl=US&pli=1
- The surfr app runs in wetsuit mode and automatically creates an android broadcast on every jump: https://play.google.com/store/search?q=surfr&c=apps&hl=de&gl=US
- The Automate app intercepts surfr's broadcasts, converts them to a special format, increases the jump count, the max jump height and sends all data to the gadgetbridge app and also tells gadgetbridge to vibrate the band: https://play.google.com/store/apps/details?id=com.llamalab.automate&hl=de&gl=US
- Gadgetbridge is connected to the Mi Band 8 and sends the jump data to the Band and tells it to vibrate: https://freeyourgadget.codeberg.page/fdroid/repo/nodomain.freeyourgadget.gadgetbridge.nightly_nopebble_0.80.0-9ba96231c.apk
- The Band vibrates and displays the jump data


prerequesites
surfr
automate
gadgetbridge nightly ab xxxx, fdroid playstore release nach xxx
offizielle app
watch face app
mi fitness

customize watch face / other more data (inkl datasources)

andere bänder

other smart bands
