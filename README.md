setpermissions v0.1
by Michel Clasquin-Johnson

Written in yab using the Yabadabbadoo IDE

Setpermissions is a little utility to adjust the filepermissions, modification type and MIME type of your files. It replicates what you do when you right-click on a file in Tracker, select "Get Info" and click on the little arrow at the bottom, but setpermissions

* takes fewer mouseclicks
* recurses into folders (but see below)
* accepts files and folders via drag-and-drop

If you have downloaded old BeOS archives or programs from SourceForge you are sooner or later going to come across the message "Could not open XYZ. The file is mistakenly marked as executable. Should this be fixed?" If it is just the one file you just click "Proceed". But what if there are twenty of them? With Setpermissions, you can load the entire folder, make all files in it readable, writable and non-executable with three clicks, then drop the actual program file onto Setpermissions and make that executable again.

Setpermissions does not distinguish between "owner", "group" and "other" permissions - each of the top six buttons will change ALL three. I may revisit that if Haiku ever goes multi-user, but for a single-user OS, the whole threefold scheme is frankly overkill.

I have also seen files with improbably early date-stamps on them. A file last modified in 1963? Really? Setpermissions lets you set a file or all files in a folder to a accessed/modified datestamp of NOW.

Finally, Setpermissions lets you do a forced MIME type recognition on a file or a folder. This is probably the least useful function, since Tracker's "Identify" function does this quite well. But I had space left for one button and now you can do this in the same interface.

To use Setpermissions drop either a single file or a single folder onto the box marked "Drop file or folder here". If it is a folder you may choose whether you want to recurse the action using the checkbox in the bottom-left corner. Now just click the button you require. 

Setpermissions does not accept multiple file drops. If necessary, make a temporary folder on your desktop, move your files into it and drop the folder onto Setpermissions.

The program is essentially a front-end for the chmod, touch and mimeset CLI commands. It also requires the ls, notify, file and stat commands and the libyab.so runtime (normally found in the yab hpkg). 

Compiling Setpermissions requires yab, yab-ide and the libclasqm_main library. Source is provided in both yabadabbadoo and yab-ide format.

You should refrain from using this utility on symbolic links. A warning dialog will appear if you drop a link onto the dropzone.

ON RECURSION

For the read-write-execute bits, you can choose whether to only change them on the folder itself (this should rarely be necessary) or whether to recurse the action to all the files and subfolders within it. The Recurse checkbox automatically comes on and is selected when you drop a folder onto Setpermissions, but you can deselect it. If you dropped a single file, it will not be available.

Setting the modification timestamp will only recurse ONE level as a safety measure. You can potentially screw up your system by changing time-stamps in /boot/config/settings (see the licensing conditions!) so this will at least contain the damage a little.

MIME type recognition ignores the checkbox and always does a full recursion, because that just is how the mimeset command works.

Setpermissions can be localized to suit the language you use with Haiku (i.e. your locale). Whether it ever will be depends on whether the Haiku community is prepared to participate. If you are familiar with computer terminology in a different language, please see the file "Localization". It won't take you more than five minutes, I promise

TODO

* Remember window position
* Open file in default app after attribute changes are complete
* Test localization once we have a few language files to work with.

LICENSE

This program is hereby placed into the Public Domain, with the following stipulations: The author, Michel Clasquin-Johnson, accepts no liability if you use this program to make your system unusable, unstable or insecure. The program manipulates important file attributes. If you don't know what those attributes are, please educate yourself before using this program.

Get it here: https://github.com/clasqm/setpermissions

Binaries: https://sourceforge.net/p/setpermissions-for-haiku/

