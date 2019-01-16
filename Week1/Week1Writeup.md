# Week 1 - Basics of Malware

## Malware

MalwareBytes defines malware as "“malicious software,” is an umbrella term that describes any malicious program or code that is harmful to systems."

There are many different kinds of malware for example a few of them are:
- viruses: Viruses are malware whose main purpose is to infect and spread to as many systems as it can either through software, hardware (usb drives), the internet, LANs, etc...
- trojans: Trojans are sneaky programs that act like safe or useful programs but are in actuality attempting to steal information/system resources from the host machine.
- Potentially Unwanted Program (PUP): PUPs are a large category of software for things like Adware which while unwanted isn't necessarily dangerous or damaging to systems.
- Ransomware: More common now than it used to be, ransomware is extremely dangerous malware that attempts to infect systems and encrypt all of the data on it and only release it when the owner pays the creator of the ransomware a fee for the password.  Generally these exchanges are made with cryptocurrencies like bitcoin.

## Why Malware?

Malware is created for a multitude of reasons, however like so many things the number one is....Money!

Other reasons include revenge, ideological reasons, boredom, corporate theft, etc...

The primary targets for malware:
1. Corporations - competitors or foreign actors attempting to steal confidential information, formulas, technology, finances
2. Governments - Foreign policy, Spying, Terrorism, Interference with elections, Military information
3. Defense Contractors - Stealing information about weapon systems or technology in order to either have it themselves or develop a countermeasure for it
4. Everyone - That's right, there is plenty of malware targeted at any computer connected to the internet in order to steal money/information from regular people

## APT

The airforce created 3 aspects of attackers when it comes to cyber warfare:
- Advanced - The attacker is skilled with modern tools/techniques/exploits and is able to develop their own based on what is required
- Persistent - The attacker has a specific target with definied goals
- Threat - The attacker is organized, supplied and funded and driven to succeed in their mission.  These can be state, corporate or criminially sponsored actors

## Fighting Back

So what can be done against the threat of malware?

The first step in combatting it is understanding it so anti-virus detection and removal tools can be created and distributed to keep systems safe from malicious code.

### Analysis

There are many ways to disect and understand malware so defenses can be created.  The simplest of which is static analysis which is about how it sounds, looking at the malware in a single point in time not while running or in a dynamic environment.  This is done by using tools to analyze the strings by dumping them from the executable to gain insight into what the code may be doing.  Additionally binary files can be attempted to be examined the same way to try and find out what it may be doing.  If the code isn't obfuscated or if that can be cracked and reverse-engineered analyzing the source code is the best form of static analysis as you can inspect exactly what the code is going to attempt to do to your system.

If that isn't enough and you have access to the malware sample.  Replication is the best way to work backwards and determine what the code is trying to do.  Replication is the process of placing the malware in a safe, isolated environment such as a VM on an air-gapped isolated machine and letting it run and tracking its path and determining what its attack vectors will be by watching what files/registry keys/processes it changes, adds, deletes or hides.  While time consuming this can provide a vast amount of useful data that can then be used to not only prevent that code from infecting other machines by updating anti-virus libraries to recognize but also if it is exploiting a weakness in a particular program that vulernability can be found and hopefully patched.

### Tools

- **Flypaper** - Flypaper is used to stop processes from shutting down in order to preserve them in memory so they can be examined before they close themselves.  Can have issues when interacting with other tools like process monitor.
- **FakeNet** - FakeNet is a network simulation tool which allows for malware that wants to connect to a remote computer/server to try to so it can be monitored and determine what it is doing and where it is going.
- **Process Monitor** - Process Monitor keeps a dynamic log of all processes, file changes, registry changes, network info, etc... which allows for the path malicious software takes to be tracked as it progresses through the system.
- **Process Explorer** - Process explorer is a more powerful version of the task manager that shows what processes and subproccesses are running on the system that can show more information about a process and has additional functionality like being able to dump strings and is linked to virustotal for checking if processes/dll's are safe.
- **FileInsight** - FileInsight is a powerful analysis and hex editing tool with a large library of plugins to examine executables and binary files to determine if something is malicious or not

