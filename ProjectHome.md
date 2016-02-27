AudioMateX Version .04

BIG DISCLAIMER:

This software is free. We wrote it because we need it and we're using it for our clients. We're happy to share, but we don't have the resources to do a lot of tech support. So, please be patient trying to get help and answers out of us!


Setup

Use the Preferences dialog to select MIDI in/out ports for each bank of faders.

If running with Pro Tools, select "AudioMateX MTC port" as the MTC port. In Pro Tools Session Setup, send MTC to "AudioMateX MTC port".

If running from timecode on tape, set the MTC port to your MIDI interface's sync port.

Check the "Autoglide" box to have faders glide back to the current automation after release during update. If "Autoglide" is not checked the faders will snap back to the current position immediately.

IMPORTANT: the app only understands 30 fps non-drop timecode.


Writing the first pass

Select the "Write" button and uncheck "Touch". This will write all faders as soon as the app receives time code.

Select the "Online" button. Move faders to the base mix position. Start Pro Tools or tape. The app will show that it is receiving timecode (display will go red). You can stop playback as soon as the app has received timecode. This will write the first pass to the end of the track. The "end" is virtual and will move as far as the highest SMPTE address received.

The document will show a "Write" pass in the "Passes" view in the document window. Double click this line to rename the pass to something interesting.

Updating

After a write pass, the app will go into update mode. If it receives timecode, the faders will write only while they are touched. If "autogllde" is enabled, they will glide back to the current automation level when released.

Each pass in "Update" will add another pass to the "Passes" view. Select a pass and hit the "Set" button to reset the automation data to that pass. Delete any passes that are unused.

Snapshots

The main window has a disclosure triangle in the upper right that reveals the snapshots view. These are global and are intended for things like "all faders at 0 dB", "all faders at -inf", etc.

To snap, put the app online, set the faders and hit the snap button. Double click the new snapshot to rename it. Select a snapshot and click restore to move faders back to the snapshot. Use the delete button to delete unused snapshots.

(The document window also has a snapshots disclosure triangle. These haven't been implemented and may not be. See timelines, below).

Documents

Save often! Although the app allows you to have multiple documents open, only the most recently opened document is active. This is a bug. The app should only allow a single document at a time.

Troubleshooting

After launching the app, hit "command-L" to bring up a live log/trace window. This will provide much information about what the app is doing, in real time. The log is also saved in /var/logs.

With the log window open, hit "command-D" to dump the current automation data to the log window.

Other Information/Known Bugs

The app hasn't gone through much testing. We've been mixing it on it from 2" and PT for a couple months, but we know our way around it. The most important thing to remember is the first "write/no touch" pass from the top of the tune. If you don't do that, nothing works.

It's only been tested with a MOTU MTP AV, although it should work with any MIDI interface that has OS X drivers.

We've seen a few instances where faders don't chase correctly when starting in the middle of a song. Backing up and playing fixes this every time.

We've been running it on 10.3.6. It's been launched and run on Tiger (10.4.2), but never on a machine connected to the console.

Mute automation is not recorded only because my console doesn't send mute information. This should be an easy fix. If your console does and you want to record some MIDI and send it up, it should be easy to add.