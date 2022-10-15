{{Quality}}
{{NotResponsible}}
{{MalwareInfobox
|name = MEMZ
|caption =
|image =MEMZMBR.jpg
|type = Trojan
|platform = Microsoft Windows
|filetype = .exe, .bat
|creator = [[User:TheTrueLeurak|Leurak]]
|date = 2015
|origin =Germany 
|aka = Trojan.Win32.MEMZ, Bootkit.Win32.MEMZ
|family = 
|pl = C++, Assembly and Python
|subtype = 
|fsize =14.5 KB (14,848 bytes) 
|size = 
|length = 
|cost = 
|cr32 =  
|md5 = 19dbec50735b5f2a72d4199c4e184960
|sha1 = 6fed7732f7cb6f59743795b2ab154a3676f4c822
|sha256 = a3d5715a81f2fbeb5f76c88c9c21eeee87142909716472f911ff6950c790c24d
|authenti = ae7f926c6a650f5783e63d3bedaa830fd05984c1b7a68f75fc9766c5dca1a1c4
|imp = 52753d226ff5a8a88caf9829928cd5d1
|ssdeep = 192:sIvxdXSQeWSg9JJS/lcIEiwqZKBkDFR43xWTM3LHn8f26gyr6yfFCj3r:sMVSaSEglcIqq3agmLc+6gyWqFCj
|vh = 014056556d15551055z20018bz13z42z183z19z}}
<!--While gratuitous swearing is obviously unacceptable, swear words that the malware in question contains should not be censored.-->

'''MEMZ''' is a custom-made [[trojan]] for [[Microsoft Windows]], originally created for the popular YouTuber [https://www.youtube.com/danooct1 Danooct1]'s ''[https://www.youtube.com/playlist?list=PLi_KYBWS_E73gG80A5YFjf8ww5H8aJvAl Viewer-Made Malware]'' series as a parody of a script kiddie's idea of dangerous [[malware]]. It has gained fame and notoriety due to its highly complex and unique [[payload]]s, many of which are based around [[internet]] memes. MEMZ is mainly thought of as a [[Joke Program|joke trojan]].

It is available as an [[executable]] .exe file and a batch version. The batch version works like a self-extracting archive, which just extracts and runs the .exe out of itself.

The MEMZ trojan is a leetspeek-style misspelling of the word "[https://en.wikipedia.org/wiki/Internet_meme Memes]". This is why most parts of this trojan contain leetspeek and random web searches, Nyan Cat, and references to Materialisimo's video "MLG Antivirus". The creator of this trojan, Leurak, makes a few Joke Programs, like the Illuminati Joke Program, and the Earthquake joke program. [https://www.youtube.com/channel/UCnye-JRGe8gWjaslsvrh63g Leurak's Channel]].

This trojan has gotten recognition ever since Danooct1 uploaded his review, for which it was originally made. Joel from ''Vinesauce'' used it in his "Windows 10 Destruction" stream, where he showcases MEMZ near the ending of the first livestream. He also thanks Danooct1 for helping with acquiring the trojan. 

Contrary to popular belief, MEMZ isn't especially destructive, nor will it render computers inoperable forever. Users with basic knowledge on how to use the PC's recovery mode can easily return their computer to normal in a few minutes at most.

The source code of MEMZ used to be found on [https://github.com/Leurak/MEMZ Leurak's GitHub], but sometime after January 14th, 2020, the Github repository was removed. The README.md file lists the dependencies, but the build procedure is – most likely intentionally – not described outright.

It is currently unknown if MEMZ or other variants of this trojan has entered the wild; Microsoft's own help desk has several questions related to MEMZ from confused (or inexperienced users) who ran the trojan without reading the warnings first, but as of 2018 there is no evidence that the trojan has been propagated through any traditional method. To prevent malicious users from deliberately spreading the trojan, currently, only versions 4 (which has the disclaimer and non-destructive version bundled with the destructive version) and up are available to download.

==Payload==
<!--Oops, I removed yer comment. Is there a vulgar language disclaimer template on here?-->
Newer versions of MEMZ Destructive, 4.0 and up, warn the user not to run it on a physical machine as it will damage it and advise the user to run the trojan on a virtual machine.

If the user answers Yes to both warning messages, MEMZ will run. At the same time, it will leave a note titled note.txt for the user saying that they are unable to use the computer anymore after rebooting it<ref>[https://github.com/Leurak/MEMZ/blob/master/WindowsTrojan/Data/Note.txt GitHub: Leurak/MEMZ/WindowsTrojan/Data/Note.txt]</ref>:
<!--Once again: don't make shitstorms over swear words if they're part of the malware being described. Oops, I just said "shit" in a comment. Welp.-->

 <code>YOUR COMPUTER HAS BEEN FUCKED BY THE MEMZ TROJAN.
 
 
 Your computer won't boot up again,
 so use it as long as you can!
 
 <nowiki>:D
        
        Trying to kill MEMZ will cause your system to be 
        destroyed instantly, so don't try it</nowiki> :D
 </code>

At the same moment, the computer's Master Boot Record is overwritten by MEMZ.

The payloads are meant to work on Windows XP and up, failing on all previous versions of Windows due to missing API calls.

MEMZ Destructive launches multiple instances of itself - one renders the payloads, while the other guard each other and trigger killWindows()<ref>[https://github.com/Leurak/MEMZ/blob/master/WindowsTrojan/Source/Destructive/KillWindows.c GitHub: Leurak/MEMZ/WindowsTrojan/Source/Destructive/KillWindows.c]</ref>, which creates a rain of message boxes and crashes the PC as elaborated further down.

The MBR payload written while note.txt gets opened is a "Nyan Cat" animation running as a custom bootloader, and this write is likely to break your partition table. If the installed system uses an EFI bootloader, "Nyan Cat" does not appear on startup due to different booting schemes, but the computer will still fail to boot as the EFI system partition will be impossible to find due to the partition table being broken.

The first payload inside of Windows is opening random websites, as well as Google searches at ''Google.co.ck'' (.ck is the country code top-level domain for the Cook Islands). The following can appear<ref>[https://github.com/Leurak/MEMZ/blob/master/WindowsTrojan/Data/Sites.txt GitHub: Leurak/MEMZ/WindowsTrojan/Data/Sites.txt]</ref>:
*''Google.co.ck'' web searches for...
**best way to kill yourself
**how 2 remove a virus
**mcaffee vs norton
**how to send a virus to my friend
**minecraft hax download no virus
**how to get money
**bonzi buddy download free
**how 2 buy weed
**how 2 get weed out of ur system
**how to code a virus in visual basic
**what happens if you delete system32
**g3t r3kt
**batch virus download
**virus.exe
**internet explorer is the best browser
**facebook hacking tool free download no virus working 2016
**virus builder legit free download
**how to create your own [[ransomware]]
**how to remove memz trojan virus
**my computer is doing weird things wtf is happenin plz halp
**dank memz
**how to download memz
**half life 3 release date
**is illuminati real
**montage parody making program 2016
**the memz are real
**stanky danky maymays
**john cena midi legit not converted
**vinesauce meme collection
**skrillex scay onster an nice sprites midi
*''answers.microsoft.com/en-us/protect/forum/protect_other-protect_scanning/memz-malwarevirus-trojan-completely-destroying/268bc1c2-39f4-42f8-90c2-597a673b6b45''
*''motherboard.vice.com/read/watch-this-malware-turn-a-computer-into-a-digital-hellscape''
*''play.clubpenguin.com'' (redirects to ''www.Disney.com as Club Penguin and Club Penguin Island have shut down'')
*[[PC Optimizer Pro|''pcoptimizerpro.com'']]
*[[Softonic|''softonic.com'']]

It may also open one of the following Windows applications:
*''calc.exe'' (Calculator)
*''notepad.exe'' (Notepad)
*''cmd.exe'' (Command Prompt)
*''write.exe'' (WordPad)
*''regedit.exe'' (Registry Editor)
*''explorer.exe'' (Windows Explorer)
*''taskmgr.exe'' (Task Manager)
*''msconfig.exe'' (System Configuration)
*''mspaint.exe'' (Paint)
*''devmgmt.msc'' (Device Manager)
*''control.exe'' (Control Panel)
*''mmc.exe'' (Microsoft Management Console)
After a while, the trojan starts randomly moving the mouse slightly, and messages taunting the user appear (see image), getting more violent and rapid as time progresses. A bit later, warning icons get drawn at random coordinates and error icons get drawn below the cursor by PayloadDrawErrors, the trojan plays error sounds through the PayloadSound payload, and the PayloadTunnel payload copies your screen's contents and place them on top of your screen, getting smaller and smaller each time (known as the "Tunnel" effect). It gets faster as time passes on. 

Trying to end the MEMZ process will, as mentioned above, start killWindows(), which pops up tons of message boxes containing "leetspeek" messages, and then crash the computer to a BSOD using NtRaiseHardError, an undocumented ntdll call, with error code 0xC0000022.

Here is a list of the messages that this payload shows<ref>[https://github.com/Leurak/MEMZ/blob/master/WindowsTrojan/Data/KillMessages.txt GitHub: Leurak/MEMZ/WindowsTrojan/Data/killMessages.txt]</ref>:
*YOU KILLED MY TROJAN! Now you are going to die.
*REST IN PISS, FOREVER MISS
*I WARNED YOU...
*HAHA N00B L2P G3T R3KT
*You failed at your 1337 h4x0r skillz
*YOU TRIED SO HARD AND GOT SO FAR, BUT IN THE END, YOUR PC WAS STILL FUCKED!
*HACKER! ENJOY BAN!
*GET BETTER HAX NEXT TIME xD
*HAVE FUN TRYING TO RESTORE YOUR DATA :D
*|\\/|3|\\/|2
*BSOD INCOMING
*VIRUS PRANK (GONE WRONG)
*ENJOY THE NYAN CAT
*Get dank antivirus m9!
*[[You Are An Idiot (1 and 2)|You are an idiot! HA HA HA HA HA HA HA]]
*<nowiki>#</nowiki>MakeMalwareGreatAgain
*SOMEBODY ONCE TOLD ME THE MEMZ ARE GONNA ROLL ME
*Why did you even tried to kill MEMZ? Your PC is fucked anyway.
*SecureBoot sucks.
*gr8 m8 i r8 8/8
*Have you tried turning it off and on again?
*<nowiki><Insert Joel quote here></nowiki>
*Greetings to all GAiA members!
*Well, hello there. I don't believe we've been properly introduced. I'm [[BonziBUDDY|Bonzi]]!
**'This is everything I want in my computer' – danooct1 2016 (not included in the original version)
**'Uh, Club Penguin. Time to get banned!' – danooct1 2016 (not included in the original version)

Restarting the computer shows the final [[payload]], dropped earlier during the MBR overwrite (this also works on Windows 2000/ME and below, but does not work with systems that use EFI bootloaders). Instead of booting into the operating system, the computer will display the message using a typewriter effect:
 "Your computer has been trashed by the MEMZ Trojan. Now enjoy the Nyan Cat..."
This is followed by an animation of the Nyan Cat being played with the PC speakers producing the well-known soundtrack for the animation.

The last payload may not always work, and the computer may boot normally. If the installed system uses an EFI bootloader, the computer still boots without Nyan Cat due to the different boot process. However, the partition table is still destroyed and the EFI system partition cannot be found.
* Random websites/random web searches open and random applications being opened ''(PayloadExecute)''
* Movement of the mouse cursor ''(PayloadCursor)''
* Random keyboard input ''(PayloadKeyboard)''
* Error sounds (varies by the operating system) ''(PayloadSound)''
* Inverting colors ''(PayloadInvert)''
* Message boxes popping up ''(PayloadMessageBox)''
* Drawing error icons ''(PayloadDrawErrors)''
* Most text reversed (including the Start button text in Windows XP) ''(PayloadReverseText)''
* Screencap whole screen ("tunnel effect") ''(PayloadTunnel)''
* Screen glitches occur ''(PayloadScreenGlitches)''
* MBR is overwritten. Partition table may also be destroyed. (part of Destructive/Main.c)

''Other payloads (added later)''
* random 8-bit sounds in the style of the Crazy Bus game ''(PayloadCrazyBus)''<ref>[https://github.com/Leurak/MEMZ/blob/master/WindowsTrojan/Source/Payloads/PayloadCrazyBus.c GitHub: Leurak/MEMZ/WindowsTrojan/Source/Payloads/PayloadCrazyBus.c]</ref>

=== Clean Version ===
MEMZ 4.0 Clean Version is a benign version of the trojan, which allows users to replicate the trojan's audiovisual payloads itself. This version does not include the MBR overwrite, therefore allowing the PC to operate even after reboot, and uses a dialog box for triggering/toggling payloads.

Leurak, the creator of the MEMZ trojan, recommends that the clean version of MEMZ is first tested on a virtual machine before it is used on a real one.

=== VineMEMZ ===
VineMEMZ is a variant of MEMZ, created for Vinesauce Joel's ''Windows 10 Destruction''. It is modified to only include ''Vinesauce''-specific memes, like [[BonziBUDDY]] and the "burning super-death sword" from [[CursorMania]].

When started it will open a note saying:
 <code>Thanks Joel for showing off my trojan on stream!
 Please wait some time until the last payload activates, which is a very special one.</code>
At the same time, the alternate MBR payload gets written.
=== Payloads ===
The background changes to an edited version of a picture of Peter Norton, from Mac Destruction. The virus can play a MIDI version of "Scary Monsters and Nice Sprites" by Skrillex. The virus spawns an animated Christmas tree on the Desktop. The virus can search random websites and web searches of a different variety, such as "[http://knowyourmeme.com/memes/giivasunner-siivagunner snow halation] midi". The cursor can change to the "burning super-death sword" from [[CursorMania]]. The virus can spraypaint a simplistic penis with the MS Paint spray tool to the desktop, accompanied by the Joel quote: "Who's been drawing DICKS?. The virus makes multiple copies of a picture of John Cena appear and move over the desktop in a wave pattern in reference to Windows 8 Destruction by Vinesauce Joel.

The virus can make the screen color-shifts slightly about once per second. The virus then plays random sounds: "succ" and "kup teraz" both courtesy of Joel, from Windows XP Destruction, as well as the 8-bit Crazy Bus-style sounds from the original MEMZ. The virus can play instructional audio from the download website [[Softonic]] is played. After a while, the final payload occurs, where is terminated, the screen goes black, and then after a few message boxes, a BonziBUDDY copy is run with a button to end the process. Ending the process will crash the computer. The MBR payload is replaced with a modified version of the title screen of the bootleg Mario game "7 GRAND DAD" which Joel once played, with the Mario lookalike replaced by Felix the Cat ripping his face open, which is taken from an unlicensed Felix the Cat game for the Sega Genesis that Joel played on a different stream. The text "PUSH START BUTTON!" is replaced with "Thanks Joel for your awesome Streams!".

=== Removal ===
The destructive version of MEMZ overwrites the first 64 KB of the boot drive. This affects the MBR and the partition table. By using bootable recovery media, such as a Windows installation disc or Linux-based live media, it is possible to recover from this.
== Media ==
<gallery>
MEMZ Removal.0 - Removal Video|MEMZ can be killed with tools provided by Windows using the command ''taskkill /f /im MEMZ.exe''.
Error lol.png|The "still using this computer?" error message.
Ezgif.com-video-to-gif (3).gif|The custom Nyan Cat MBR.
Rip pc.png|An example of some of the error messages when MEMZ.exe is closed.
MEMZtrojanwin.jpg
VineMEMZ (Win32)|Danooct1's video on VineMEMZ.
Capture-0.PNG|Windows reinstall setting.
</gallery>
==References==
{{reflist}}[[es:MEMZ]]
[[pl:MEMZ]]
[[zh:MEMZ]]
[[Category:Trojan]]
[[Category:Win32]]
[[Category:Virus]]
[[Category:Win32 trojan]]
[[Category:Win32 virus]]
[[Category:BAT]]
[[Category:Trojan dropper]]
[[Category:Microsoft Windows]]
[[Category:MBR overwriting viruses]]
