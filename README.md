# How to NOT get ratted in the Minecraft Community

This small tutorial will inform you about what you should and shouldn't do when running 3rd-party MC modifications like Fabric/Forge mods, MCPs and building Open Source projects. First, we have to address that a Logger and a RAT are NOT the same thing. RAT, which stands for Remote Access Trojan, allows the attacker to gain control over your PC and possibly spy on you, keeping up to date with your activity. A Logger is a program that can steal your browser cookies, documents, videos, photos, etc. I will be talking about tips and tricks that could once save your phyisical PC from this. This tutorial mostly applies to Java applications only.

**1. Check if a JAR file is infected** <br>
If the suspected file doesn't use Native Obfuscation or isn't encrypted, continue reading this. It's good to use a RE (reverse engineering) tool like [Recaf](https://github.com/Col-E/Recaf) to check for references in JAR files that contain "URL," "Http," or "Socket," which can allow the suspicious file to make connections. Seeing these references doesn't instantly mean that the application contains malicious code although it does increase the chances of the file being malicious. If the JAR is obfuscated and you don't want to do any further analysis, consider asking the person that sent you the JAR file questions that could maybe explain why there are these references and what they are for.

**2. Check if an FOSS/Buildable application is clean** <br>
If you happen to download a buildable source code of a client or a minecraft mod from GitHub or any other platform, it's important to check it first before building it and using it, since it's not guaranteed that it's safe. You should always first check if there is any RAT in the code of the application before compiling it without being aware of it. Whenever something is FOSS (free open-source software), it doesn't always mean that there can't be any malicious code. If the application uses Gradle, the next thing you should 100% do is check if the Gradle Wrapper  contains any malicious code or links, build script for links to malicious libraries/JAR's and gradlew.bat for malicious code. This isn't that common anymore, but lots of people aren't aware that it's possible to infect a Gradle wrapper or any of these files. You should still always check it for your own safety, even after I told you that it's not that common anymore. The average size of a Gradle wrapper is around 55KB. Check it even if it's around that size since it can be compromised with a small amount of code that can download a malicious file and execute with less than 10 lines of code. Now, even if the application is using Maven or Gradle, you should always check the build script to make sure that it's not going to implement any malicious code into your build of the application.

**3. Run suspicious files offline** <br>
If you happen to download a JAR file from an unknown source and you aren't sure if it's safe to use, you should either run it offline or not at all. Even though running files offline isn't the safest thing too since they can write/put files into places like startup, which could be dangerous once reconnecting to your WiFi. Do this only if you are lazy/don't want to do any of these other tips.

**4. Use a VM (Virtual Machine) when running suspicious files** <br>
This is one of the best things you can do to protect yourself from dangerous files and basically assures you that your local PC will NEVER get infected. If you don't know what a Virtual Machine is, it's basically a Virtual PC inside your Physical PC. These VMs usually have very good isolation and make sure that no infected file escapes and spreads into your local PC. If you are looking forward to using VMs (which you should), use VMs like [VirtualBox](https://www.virtualbox.org) or [VMware](https://www.vmware.com) (Here are some [VMware codes](https://gist.github.com/PurpleVibe32/30a802c3c8ec902e1487024cdea26251). If you are new to this, you should for sure use VirtualBox, but if you have a somewhat decent knowledge, use VMware. Here are also some setup guides + tips and tricks.

How to set up VMware: https://www.youtube.com/watch?v=7kcqDy7aeGg <br>
How to set up Virtual Box: https://www.youtube.com/watch?v=sBzL_zoYt6o <br>
How to speed up your VM: https://www.youtube.com/watch?v=fGMvH2zYr7Q&t <br>
VM Undetected for VirtualBox: https://github.com/Scrut1ny/VM-Undetected <br>

**5. Pretend your PC is a VM (Virtual Machine)** <br>
Sometimes, when malware detects registries, processes, or file paths related to a VM, it terminates itself to prevent any kind of dynamic analysis that could expose the malicious code. However, if we can spoof a legitimate PC as a VM, we could prevent any sort of malicious code from executing... ONLY if the malware VM checks. If the malware has one, then you will be lucky to make it out safe without your PC getting infected. But if the malware does not have one, your PC will pay the price. Luckily, there is new software in its Alpha version right now that basically does what I just theorized. It can be found at [cyberscarecrow.com](https:/www.cyberscarecrow.com/), and a showcase of it can be found on [Eric Parker's](https://www.youtube.com/watch?v=zTOKEKQ8ITA) channel. Although, remember that this could cause issues with other programs that ban VMs, such as anti-cheat systems for games or paid softwares.

**6. Use a VPN (virtual private network)** <br>
If you basically don't care that your local gets infected or logged but you care if you get IP logged, this is clearly for you! This is probably one of the worst options and decisions you can make, and you shouldn't do it at all. It's only good to use VPN for running stuff online in a VM to prevent IP log but also allows you to get better output from the file that you are running. Make sure to use NAT type connections which will be compatible with your VPN but also assures you that no malicious file spreads into your local machine.

**7. Block commonly used websites with the webhook feature** <br>
If you basically want to eliminate 99% of Loggers in this community, this is for you. Most of the people that make loggers use Discord's webhook feature which allows them to get the stuff that they want from your PC. If you decide to not use Discord, you can simply blacklist Discord's DNS which makes sure that the malicious people don't receive any files or anything about you even if you are online. The Discord webhook feature is just an example. There are many more websites with webhook features which you can blacklist.

**8. Do NOT rely on RAT checking programs** <br>
This is the most important thing to NOT do if you want to check if something contains malicious code. These rats checkers are 99% of the time really bad or simply will only tell you that code is obfuscated or that it throws exceptions. If u consider that as a rat check, then I don't know how your PC is gonna end up in the future. https://isthisarat.com is a great example of garbage which is basically sign based and can only detect the worst rats of all time. If u really want to use a RAT checker (Which is still not recommended), you can use [Theia Checker](https://github.com/Tigermouthbear/Theia) which is mainly good for its feature where it can tell you if the JAR has referenced any imports related to web connection.

**9. Do your background research** <br>
This is something that really doesn't stick out that much anymore but is one of the most important things when trying to understand if someone has malicious intent. Usually, if someone is going to be sending you a malicious program, they will be using social engineering which is a way to get people to do things they shouldn't like give up passwords or click on links that can harm their computer or run malicious programs. They can be trying to impersonate someone that you know and eventually sending you a malicious file with something along the lines of "Does this client work for you?" or they can be someone random that you basically never really heard of which would be trying to gain your trust and make you run a malicious file. If you think that the person is trying to pull tricks like these ones on you, check if they have any social media or ask others if they know the person, what are they mainly known for, if they have done any malicious stuff or have been involved in something like this before which could make you aware about the situation and give you a better understanding over someones intentions. You should also ask questions and be as concerned as possible if you are still suspecting something.

## Credits: <br>
**3000IQPlay -** Writing this tutorial, fully speaking from experience. <br>
**ChatGPT and exotic -** Fixing grammar. <br>
