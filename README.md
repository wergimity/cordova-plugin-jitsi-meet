# cordova-plugin-jitsi-meet
Cordova plugin for jitsi meet react native sdk

I created this repo as there were multiple versions of this plugin, one which worked for iOS and Android, but neither worked with both. This verison satisfies the 64bit requirement for Android and also works in iOS and is currently being used in production.

# Installation
`cordova plugin add https://github.com/findmate/cordova-plugin-jitsi-meet`

# Usage
```
const roomId = 'your-custom-room-id';

jitsiplugin.loadURL('https://meet.jit.si/' + roomId, roomId, false, function (data) {
    if (data === "CONFERENCE_WILL_LEAVE") {
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

On iOS/Xcode you will need to manually specify the WebRTC and JitsiMeet frameworks manually to be embedded.
