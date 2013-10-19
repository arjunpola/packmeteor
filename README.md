Pack Meteor
===========

This is a simple CLI for packaging the Meteor client into a folder. Its useful when creating `Chrome Packaged Apps` but can also be used with `Cordova`.

###Installation:
```
$ npm install packmeteor
```

Rig a Meteor app on `localhost:3000` and install the `appcache` package

Create packaged app folder:
```
$ packmeteor -c hello
```
###Chrome packaged apps
Autobuild and reload Chrome Packaged App on Meteor hotcode push:
```
$ cd hello
$ packmeteor -ar
```
*NOTE: Chrome + Mac OS X -> Close the Chrome before running the script. Current chrome requires manual refresh of the app, goto [chrome://extensions/](chrome://extensions/) and click "update"*

###Cordova
Autobuild Cordova:
```
packmeteor -ae
```
*This will autopackage and update android emulator*

###Directly from filesystem
Run the packaged client app without server:
Simply open the `index.html` from finder / file explorer

###Usage:
```
$ packmeteor --help

  Usage: packmeteor [options]

  Options:

    -h, --help                        output usage information
    -V, --version                     output the version number
    -c, --create <name>               Create Packaged App
    -a, --autobuild                   Auto build on server update
    -r, --reload                      Reload app
    -b, --build [url]                 Client code url [http://localhost:3000]
    -s, --server <url>                Server url, default to build url [http://localhost:3000]
    -t, --target [packaged, cordova]  Target platform, default is autodetect
    -e, --emulate [platform]          Reload emulator [android]
    -d, --device [platform]           Reload device [android]
    -m, --migration                   Enable Meteor hotcode push
```

###Build from server
The script packages the app from the Meteor app at localhost:3000 (default)
Use `-b http://myclient.com:80` for building the app from this location instead.

###Connection client to server
The packaged client is mounted to the same server as the build server or current ip if could be found. But there may be cases where the client should connect to a different server.
Use `-s http://livedataserver.com:80`


Kind regards Morten, aka @raix
