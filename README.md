# cordova-plugin-jitsi
Cordova plugin for Jitsi Meet React Native SDK. Works with both iOS and Android, and fixes the 64-bit binary dependency issue with Android found in previous versions of this plugin.

# Summary 
This is based on the repo by findmate, but I updated the JitsiMeet SDK and WebRTC framework to the latest version, to get all features working in a Cordova app.
The original repo is here: https://github.com/agorum/cordova-plugin-jitsi

# Installation
`cordova plugin add https://github.com/amarnathduttaroy/cordova-plugin-jitsi`

## iOS Installation
On iOS/Xcode you will need to manually specify the WebRTC and JitsiMeet frameworks manually to be embedded.

Example of how to select them here: https://github.com/seamlink-dev/cordova-plugin-jitsi-meet/blob/master/xcode-ios-framework-embed-example.png


# Usage
```
const roomId = 'your-custom-room-id';

jitsiplugin.join('https://meet.jit.si/', roomId, false, function (data) {
    if (data === "CONFERENCE_TERMINATED") {
        jitsiplugin.destroy(function (data) {
            // call finished
        }, function (err) {
            console.log(err);
        });
    }
}, function (err) {
    console.log(err);
});
```
