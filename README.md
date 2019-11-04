MumbleEchoSpatializer
=====================

Mumble spatial audio plugin for Echo VR.

Tested on Mumble 1.3.0.

Installation
------------
From the [Releases](https://github.com/qlyoung/MumbleEchoSpatializer/releases)
page, download and copy both .dll files into `%AppData%/Mumble/Plugins`. Restart
Mumble. Go to Configure -> Settings -> Plugins and verify that "Echo VR (latest)"
appears in the list. Check "Link to Game and Transmit Position" under "Options".
Go to "Audio Output" and check "Positional Audio".

Usage
-----
Audio will be spatialized while a match is in progress and actively being
played. Pre- and post-match states will not have spatialized audio.

Mumble settings for positional audio will need to be adjusted for best
experience. Go to Configure -> Settings -> Audio Output and check the
"Positional Audio" box. In the Positional Audio section make the following
changes:

- Check "Headphones"
- Minimum Distance = 1.0m
- Maximum Distance >= 80.0m
- Minimum Volume = 5%

Troubleshooting
---------------
- Verify that Echo VR is running
- Verify that Mumble is running

In Mumble settings, under "Audio Output":
- Verify that the device is set to your Rift headphones
- Verify that the "Positional Audio" checkbox is [x] checked
- Under "Positional Audio", verify that the "Headphones" checkbox is [x]
  checked

In Mumble settings, under "Plugins":
- Under "Options", verify that the "Link to Game and Transmit Position"
  checkbox is [x] checked
- Under "Plugins", verify that "Echo VR" is present in the list
  - If it is not, you probably installed the wrong plugin version (32 or 64
    bit), or the plugin is missing; reinstall it
- Under "Plugins", verify that the checkbox next to "Echo VR" is [x] checked

Once you have checked all of the above:
- In the Mumble status pane (on the left), wait 30 seconds and ensure "Echo VR
  linked" appears. If it does not, start over from the beginning of this list.

If *none* of the above work:
- **While in a match**, go to http://localhost/session in your browser, and
  verify that you get a text blob (page does not time out). If it is timing
  out, *turn off your firewall* or make an exception for Echo VR.

Contributing
------------
Patches are welcome. Please use the following guidelines:
- Patches should use the line endings and style of the changed file
- Contributions must be public-domain, as specified in the
  [Unlicense](https://unlicense.org)


Building
--------
Clone the project and import it with VS2015 (no other version will work). All
dependencies are included. Build in release mode only; Mumble does not expect
debugging symbols in its plugin DLLs and they will corrupt Mumble address
space.
