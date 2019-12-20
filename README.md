# Restart Remote management/Screen sharing

## Problem: 

Remote management/Screen sharing stop working after screen locked on the client machine before tacking control. 

## Solution:

Connect to the remote mac via ssh and kill the screensharing service, launchctl restarts it automatically.

 ```sh
 sudo launchctl kill KILL system/com.apple.screensharing
```

Also the legacy commands could be used:

 ```sh
 sudo launchctl unload /System/Library/LaunchDaemons/com.apple.screensharing.plist  
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.screensharing.plist
```
