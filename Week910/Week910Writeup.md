# Week 9-10 - Mobile Security

## Intro

This weeks discussion was about mobile security specifically android security but we touched on iOS and other mobile operating systems as well as the history of mobile security. The mobile phone industry has exploded not only in terms of size but also in complexity and technology involved.  Once phones started getting "smart" features and full operating systems there were many competing players in the market from Blackberry, Windows, etc... However over the last few years Android and iOS are the only real players left in the smartphone market with android having the lionshare of the market.

## History

Motorola invented the first experimental cell phone back in 1973 and released the first commercially available cell phone in 1984.  These phones ran on the analog cell phone network AMPS also designated as (1G) as it was the first generation cell phone network. 

<img src="cellHistory.JPG" alt="history" class="inline"/>

As shown in the above graph charting the evolution of the cell phone network you can see how and why the complexity of mobile security has gotten vastly more complicated in a few short decades.  Going from analog signals where the worst that could be done was either cloning of phones to steal minutes and make calls on someone else's account or jamming of the signal to prevent mobile phone conversations.  From there once the networks went digital both additional security was added as well as the addition of malware and additional security in the form of encryption and jamming resistance. 

From there the next big leap in mobile networking technology was the inclusion of internet and data which while also brought new security features like encrypted voice and data, additional security hardware like SIM cards and additional encryption, it also allowed the vast majority of the kinds of malware being seen today to be able to be distributed and cause damage/steal information.

## APK Files

Android package files are zipped directories made up of a variety of different kinds of files, some of those include:

- Assets - Where files of all kinds are included by the app for things such as images, fonts, etc... Additionally a common location for malware to insert itself
- AndroidManifest.xml - location of app metadata and where entrypoints are defined
- classes.dex - Dalvik Java executable files
- lib - library files

## Malware

When it comes to android specific malware a few types of examples are:
- Banking Trojans - Banking Trojans are malware that specifically target banking information like username and password credentials.  They go about this by generally first attempting to bypass 2 factor authentication.  Banking trojans are complicated multi-step processes as they generally begin with attempting to phish a potential victim into going to a fake banking page in attempt to get the victim to log in and potentially download for a banking application.  Of course the application is infected with malware that can intercept any 2 factor authentication messages from the bank legitmately so when the attackers make withdrawls the victim isn't notified and their phones allow the transactions to process. 
- Bootkits - Bootkits are pre-installed malware that is extremely difficult to get rid of.  They already have root access so if there are any other pieces of malware on the phone in terms of keyloggers or untrustworthy apps even if the user uninstalls those apps they will be reinstalled by the phone usually on the next reboot cycle.
- Botnets - Botnets on phones behave similarly to those of infected computers; however, the method of infection is either by getting the user to click on a infected URL or by including the malicious payload in an app that the victim downloads.  Once on the phone they can be controlled remotely to do any number of damaging functions such as being a part of a DDOS attack, recording banking/user data, sending calls/texts in an attempt to infect people in the victims contacts, etc...
- Worms - Mobile worms are again similar to their PC based cousins in the fact that the ultimate goal is to spread and infect.  While there is generally a secondary payload attached or added later the worm is attempting to get as many other people infected generally through malicious SMS messages or social media messenging apps of a victims entire contact list.  This is ususally done in the background so the victim doesn't have any knowledge that these messages are being sent from their device.

## Tools
- APKTool - APKTool is a useful tool that can reverse engineer 3rd party binary android applications. It has the ability to decode and rebuild resources as well as analyzing entry points and XML permissions.
- dex2jar - dex2jar is a group of 4 tools that allow for the reading and writing of Dalvik Executable (.dex) files. The conversion of .dex filess to .jar files. The assembly and disassembly of .dex files to smali files as well as the decryption of strings in .jar files.
- JD-GUI - JD-GUI is a utility that can display the java source code of .class files.  The constructed source code can then be used to gain access to variables and functions of the code.  Very useful for reverse engineering
- Emulator - Emulators are pieces of software that mimic ususally a set of hardware in order to run specific programs.  With relation to this week the emulator in question is an android emulator that can allow a user to simulate and run the android operating system on their computers instead of needing to run it on a mobile device.  This allows for reverse engineering and development to be done on a PC environment.
- AXMLPrinter2 - Converts android binary XML into human readable XML files
- Androguard - Androguard is a set of python tools that allow for the inspection and reverse engineering of android files. This can be done through DEX, ODEX, APK, binary XMLs and android resources by disassembling and decompiling the files.
- JadX - JadX is a .dex file to java decompiler.
