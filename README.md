<h1><b> Mission: ARP</b></h1>

#
<img src="https://img.shields.io/badge/Python-3.10.5-blue"> <img src="https://img.shields.io/badge/Status-Final-orange"> <img src="https://img.shields.io/badge/FinalVersion-red"> <img src="https://img.shields.io/badge/Licence-MIT-yellowgreen">

#
<h1><b> What is the ARP Protocol? </b></h1>
<h2><i>Address Resolution Protocol (ARP) is a protocol that enables network communications to reach a specific device on the network. ARP translates Internet Protocol (IP) addresses to a Media Access Control (MAC) address, and vice versa. Most commonly, devices use ARP to contact the router or gateway that enables them to connect to the Internet.

Hosts maintain an ARP cache, a mapping table between IP addresses and MAC addresses, and use it to connect to destinations on the network. If the host doesn’t know the MAC address for a certain IP address, it sends out an ARP request packet, asking other machines on the network for the matching MAC address. 

The ARP protocol was not designed for security, so it does not verify that a response to an ARP request really comes from an authorized party. It also lets hosts accept ARP responses even if they never sent out a request. This is a weak point in the ARP protocol, which opens the door to ARP spoofing attacks.

ARP only works with 32-bit IP addresses in the older IPv4 standard. The newer IPv6 protocol uses a different protocol, Neighbor Discovery Protocol (NDP), which is secure and uses cryptographic keys to verify host identities. However, since most of the Internet still uses the older IPv4 protocol, ARP remains in wide use.</i></h2>

#

<h1><b> What is ARP Spoofing (ARP Poisoning)? </b></h1>
<h2><i>An ARP spoofing, also known as ARP poisoning, is a Man in the Middle (MitM) attack that allows attackers to intercept communication between network devices. The attack works as follows:

1.    The attacker must have access to the network. They scan the network to determine the IP addresses of at least two devices⁠—let’s say these are a workstation and a router. 

2.    The attacker uses a spoofing tool, such as Arpspoof or Driftnet, to send out forged ARP responses. 

3.    The forged responses advertise that the correct MAC address for both IP addresses, belonging to the router and workstation, is the attacker’s MAC address. This fools both router and workstation to connect to the attacker’s machine, instead of to each other.

4.    The two devices update their ARP cache entries and from that point onwards, communicate with the attacker instead of directly with each other.

5.    The attacker is now secretly in the middle of all communications.
</i></h2>
<h2><b> Know Your Limit :</b></h2>

> git clone https://github.com/R3DHULK/mission-arp<br>
> cd mission-arp<br>
> sudo python arp-spoofing.py<br>
#
<img src ="https://www.imperva.com/learn/wp-content/uploads/sites/13/2020/03/thumbnail_he-ARP-spoofing-attacker-pretends-to-be-both-sides-of-a-network-communication-channel.jpg.webp">

#
<h1><b> Once the attacker succeeds in an ARP spoofing attack, they can:</b></h1>
<h2><i>
⚫    Continue routing the communications as-is⁠—the attacker can sniff the packets and steal data, except if it is transferred over an encrypted channel like HTTPS. <br>
⚫    Perform session hijacking⁠—if the attacker obtains a session ID, they can gain access to accounts the user is currently logged into.<br>
⚫    Alter communication⁠—for example pushing a malicious file or website to the workstation.<br>
⚫    Distributed Denial of Service (DDoS)⁠—the attackers can provide the MAC address of a server they wish to attack with DDoS, instead of their own machine. If they do this for a large number of IPs, the target server will be bombarded with traffic.<br></i></h2>

#
<h1><b>How to Detect an ARP Cache Poisoning Attack<b></h1>
<h2><i>Here is a simple way to detect that a specific device’s ARP cache has been poisoned, using the command line. Start an operating system shell as an administrator. Use the following command to display the ARP table, on both Windows and Linux:</i></h2>
<br>

```
sudo python arp-spoofing-detect.py 

or 

sudo python arp-spoofing-detectv2.py
```

#
<h1><b>ARP Spoofing Prevention</b></h1>
<h2><i>Here are a few best practices that can help you prevent ARP Spoofing on your network:<br></br>

🔴    Use a Virtual Private Network (VPN)⁠—a VPN allows devices to connect to the Internet through an encrypted tunnel. This makes all communication encrypted, and worthless for an ARP spoofing attacker.<br>

🔴    Use static ARP⁠—the ARP protocol lets you define a static ARP entry for an IP address, and prevent devices from listening on ARP responses for that address. For example, if a workstation always connects to the same router, you can define a static ARP entry for that router, preventing an attack.<br>

🔴    Use packet filtering⁠—packet filtering solutions can identify poisoned ARP packets by seeing that they contain conflicting source information, and stop them before they reach devices on your network.<br>

🔴    Run a spoofing attack⁠—check if your existing defenses are working by mounting a spoofing attack, in coordination with IT and security teams. If the attack succeeds, identify weak points in your defensive measures and remediate them.<br>
</h2></i>
<br>

#
<h1 align="left"><b>Support 👇👇👇 </b></h1>
<a href="https://www.buymeacoffee.com/r3dhulk"> <img align="left" src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="50" width="210" alt="https://www.buymeacoffee.com/r3dhulk" /></a><br><br>
