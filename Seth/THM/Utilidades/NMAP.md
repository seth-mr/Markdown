![[Pasted image 20250824190651.png]]

![[Pasted image 20250824215548.png]]
# who is online ?

nmap use multiple ways to **specify its targets**.

**ip range** using **-** if you want to scan all the ip addresses from 192.168.0.1 yo 192.168.0.10 yo can write 192.168.0.1-10.

**ip subnet** using **/** if you want to scan subnet, you can express it as 192.168.0.1/24 and it was equivalent to 192.168.0.0-255

**Hostname** you can also specify the target by hostname, for example **example.thm** 

Lets say you want to *discover the online hosts on a network.*  Nmap offer the **-an** option.

## Scanning a "Local" Network

we use local to refer to the network we are directly connected to.

in this example *our ip addres is 192.168.66.89* and we are *scanning the 192.168.66.0/24* network 

`nmap -sn 192.168.66.0/24`

![[Pasted image 20250824183446.png]]

Because we are scanning the local network we can look up the MAC addresses of the devices.

whe can scanning directly connected network, Nmao starts by sending ARP request. when a device responds. Nmap labels it with "Host is up"

## Scanning a "Local" Network

in this context remote means at least one router separetes our system from this network.

thes means our traffic must go trough  one or more routers. this means we cannot send ARP request to the target.

Our system has the ip address 192.168.66.89 and belong to the 192.168.66.0/24 network, in the terminal below we scan the target network 192.168.11.0/24. where there ara two or more routers (hops) separate our local system from the target hosts.


![[Pasted image 20250824184312.png]]

The output shows that five hosts are up. but how we now this?

- 192.168.11.1 is *live and responded to the ICMP echo(ping request)*
- 192.168.11.2 seems down. Nmap sent two ICMP echo (ping) requests, two ICMP timestamp requests, two TCP packets to port 443 with the SYN flag set, and two TCP packets to port 80 with the ACK flag set. The target didn’t respond to any. We observe several ICMP destination unreachable packets from the 192.168.11.151 router.
- 
![[Pasted image 20250824184628.png]]

It is worth noting that we can have more control over how Nmap discovers live hosts such as `-PS[portlist]`, `-PA[portlist]`, `-PU[portlist]` for TCP SYN, TCP ACK, and UDP discovery via the given ports. However, this is beyond the scope of this room.

As a final point, Nmap offers a list scan with the option `-sL`. This scan only lists the targets to scan without actually scanning them. For example, `nmap -sL 192.168.0.1/24` will list the 256 targets that will be scanned. This option helps confirm the targets before running the actual scan.

As we mentioned earlier, `-sn` aims to discover live hosts without attempting to discover the services running on them. This scan might be helpful if you want to discover the devices on a network without causing much noise. However, this won’t tell us which services are running. If we want to learn more about the network services running on the live hosts, we need a more “noisy” type of scan, which we will explore in the next tasksn 192
Click the **Start AttackBox** button at the top of the page and wait for it to load. Once the AttackBox is ready, open the terminal to access `nmap` and answer the questions in this and later tasks. Furthermore, click on the **Start Machine** button below to get your target system ready for later tasks.

# Who is Listening

earlier we use -sn to discover live host. now we want to *discover the network services listening on these live hosts.* By network services , we mean any process that listening for incoming connections on a TCP or UDP port.

Common networks services include web servers, which tipically listen on UDP(and TCP) port 53

## Scanning TCP Ports

the easist and basic way *to know weather TCP port is open*  would be to attemp to *telnet* to the port.

only *open TCP ports would respond appropriately* and allow a TCP connection to be established. This procedure is not very different from Nmap’s connect scan.

## Connect Scan 


The connect scan can be triggered using `-sT`. It *tries to complete the TCP three-way handshake with every target TCP port*. If the TCP port turns out to be open and Nmap connects successfully, Nmap will tear down the established connection.

In the screenshot below, our scanning machine has the IP address `192.168.124.148` and the target system has TCP port 22 open and port 23 closed. In the part marked with 1, you can see how the TCP three-way handshake was completed and later torn down with a TCP RST-ACK packet by Nmap. The part marked with 2 shows a connection attempt to a closed port, and the target system responded with a TCP RST-ACK packet.

![[Pasted image 20250824190533.png]]

## #### SYN Scan (Stealth)

Unlike the connect scan, which tries to **connect** to the target TCP port, i.e., complete a three-way handshake, the *SYN scan only executes the first step:* it sends a TCP SYN packet. Consequently, the TCP three-way handshake is never completed. The advantage is that this is expected to lead to fewer logs as the connection is never established, and hence, it is considered a relatively stealthy scan. You can select the SYN scan using the `-sS` flag.

In the screenshot below, we scan the same system with port 22 open. The part marked with 1 shows the listening service replying with a TCP SYN-ACK packet. However, Nmap responded with a TCP RST packet instead of completing the TCP three-way handshake. The part marked with 2 shows a TCP connection attempt to a closed port. In this case, the packet exchange is the same as in the connect scan.

![[Pasted image 20250824205643.png]]

##  Scanning UDP Ports

Although most services use TCP for communication, many use UDP. Examples include DNS, DHCP, NTP (Network Time Protocol), SNMP (Simple Network Management Protocol), and VoIP (Voice over IP). UDP does not require establishing a connection and tearing it down afterwards. Furthermore, it is very suitable for real-time communication, such as live broadcasts. All these are reasons to consider scanning for and discovering services listening on UDP ports.

Nmap offers the option `-sU` to scan for UDP services. Because UDP is simpler than TCP, we expect the traffic to differ. The screenshot below shows several ICMP destination unreachable (port unreachable) responses as Nmap sends UDP packets to closed UDP ports.
![[Pasted image 20250824205720.png]]

## Limiting the Target Ports
Nmap scans the most common 1,000 ports by default. However, this might not be what you are looking for. Therefore, Nmap offers you a few more options.

- `-F` is for Fast mode, which scans the 100 most common ports (instead of the default 1000).
- `-p[range]` allows you to specify a range of ports to scan. For example, `-p10-1024` scans from port 10 to port 1024, while `-p-25` will scan all the ports between 1 and 25. Note that `-p-` scans all the ports and is equivalent to `-p1-65535` and is the best option if you want to be as thorough as possible.
-   
![[Pasted image 20250824210111.png]]

## OS Detection

You can enable OS detection by adding the `-O` option. As the name implies, the OS detection option triggers Nmap to rely on various indicators to make an educated guess about the target OS. In this case, it is detecting the target has Linux 4.x or 5.x running. That’s actually true. However, there is no perfectly accurate OS detector. The statement that it is between 4.15 and 5.8 is very close as the target host’s OS is 5.15.

![[Pasted image 20250824215413.png]]

## Service and Version Detection

You discovered several open ports and want to know what services are listening on them. `-sV` enables version detection. This is very convenient for gathering more information about your target with fewer keystrokes. The terminal output below shows an additional column called “VERSION”, indicating the detected SSH server version.

![[Pasted image 20250824215503.png]]

What if you can have both `-O`, `-sV` and some more in one option? That would be `-A`. This option enables OS detection, version scanning, and traceroute, among other things.

## Forcing the Scan

When we run our port scan, such as using `-sS`, there is a possibility that the target host does not reply during the host discovery phase (e.g. a host doesn’t reply to ICMP requests). Consequently, Nmap will mark this host as down and won’t launch a port scan against it. We can ask Nmap to treat all hosts as online and port scan every host, including those that didn’t respond during the host discovery phase. This choice can be triggered by adding the `-Pn` option.

![[Pasted image 20250824215530.png]]


## TIMING: HOW FAST IS FAST

![A green rocket heading up](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/5f04259cf9bf5b57aed2c476-1723711770591.svg)  

Nmap provides various options to control the scan speed and timing.

Running your scan at its normal speed might trigger an IDS or other security solutions. It is reasonable to control how fast a scan should go. Nmap gives you six timing templates, and the names say it all: paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5). You can pick the timing template by its name or number. For example, you can add `-T0` (or `-T 0`) or `-T paranoid` to opt for the slowest timing.

In the Nmap scans below, we launch a SYN scan targeting the 100 most common TCP ports, `nmap -sS 10.201.38.125 -F`. We repeated the scan with different timings: T0, T1, T2, T3, and T4. In our lab setup, Nmap took different amounts of time to scan the 100 ports. The table below should give you an idea, but you will get different results depending on the network setup and target system.

|Timing|Total Duration|
|---|---|
|T0 (paranoid)|9.8 hours|
|T1 (sneaky)|27.53 minutes|
|T2 (polite)|40.56 seconds|
|T3 (normal)|0.15 seconds|
|T4 (aggressive)|0.13 seconds|

In the following screenshots, we can see the time when Nmap sent the different packets. In this screenshot below, with the scan timing being `T0`, we can see that Nmap waited 5 minutes before moving to the next port.

![Wireshark showing the time of the packets generated by Nmap when using T0 for timing.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/5f04259cf9bf5b57aed2c476-1723639768199.png)  

In the screenshot below, Nmap waited 15 seconds between every two ports when we set the timing to `T1`.

![Wireshark showing the time of the packets generated by Nmap when using T1 for timing.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/5f04259cf9bf5b57aed2c476-1723639781233.png)  

Then, the waiting dropped to 0.4 seconds for `T2` as shown below.

![Wireshark showing the time of the packets generated by Nmap when using T2 for timing.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/5f04259cf9bf5b57aed2c476-1723639792352.png)  

Finally, in the default case, `T3`, Nmap appeared to be running as fast as it could, as shown below. It is worth repeating that this would look different on a different lab setup. However, in this particular case, Nmap considered the connection to the target to be fast and reliable, as no packet loss was incurred.

![Wireshark showing the time of the packets generated by Nmap when using T3 for timing.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/5f04259cf9bf5b57aed2c476-1723639806781.png)  

A second helpful option is the number of parallel service probes. The number of parallel probes can be controlled with `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>`. These options can be used to set a minimum and maximum on the number of TCP and UDP port probes active simultaneously for a host group. By default, `nmap` will automatically control the number of parallel probes. If the network is performing poorly, i.e., dropping packets, the number of parallel probes might fall to one; furthermore, if the network performs flawlessly, the number of parallel probes can reach several hundred.

A similar helpful option is the `--min-rate <number>` and `--max-rate <number>`. As the names indicate, they can control the minimum and maximum rates at which `nmap` sends packets. The rate is provided as the _number of packets per second_. It is worth mentioning that the specified rate applies to the whole scan and not to a single host.

The last option we will cover in this task is `--host-timeout <time>`. This option specifies the maximum time you are willing to wait, and it is suitable for slow hosts or hosts with slow network connections.

|Option|Explanation|
|---|---|
|`-T<0-5>`|Timing template – paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5)|
|`--min-parallelism <numprobes>` and `--max-parallelism <numprobes>`|Minimum and maximum number of parallel probes|
|`--min-rate <number>` and `--max-rate <number>`|Minimum and maximum rate (packets/second)|
|`--host-timeout`|Maximum amount of time to wait for a target host|
## Output: Controlling What You See

### Verbosity and Debugging

In some cases, the scan takes a very long time to finish or to produce any output that will be displayed on the screen. Furthermore, sometimes you might be interested in more real-time information about the scan progress. The best way to get more updates about what’s happening is to enable verbose output by adding `-v`. Consider the following terminal output showing the network scan repeated twice. In the first case, we opted for the default output verbosity.

AttackBox Terminal
![[Pasted image 20250824220130.png]]
AttackBox Terminal

![[Pasted image 20250824220149.png]]

Most likely, the `-v` option is more than enough for verbose output; however, if you are still unsatisfied, you can increase the verbosity level by adding another “v” such as `-vv` or even `-vvvv`. You can also specify the verbosity level directly, for example, `-v2` and `-v4`. You can even increase the verbosity level by pressing “v” after the scan already started.  

If all this verbosity does not satisfy your needs, you must consider the `-d` for debugging-level output. Similarly, you can increase the debugging level by adding one or more “d” or by specifying the debugging level directly. The maximum level is `-d9`; before choosing that, make sure you are ready for thousands of information and debugging lines.

### Saving Scan Report

In many cases, we would need to save the scan results. Nmap gives us various formats. The three most useful are normal (human-friendly) output, XML output, and grepable output, in reference to the `grep` command. You can select the scan report format as follows:

- `-oN <filename>` - Normal output
- `-oX <filename>` - XML output
- `-oG <filename>` - `grep`-able output (useful for `grep` and `awk`)
- `-oA <basename>` - Output in all major formats

In the terminal below, we can see an example of using the `-oA` option. It resulted in three reports with the extensions `nmap`, `xml`, and `gnmap` for normal, XML, and `grep`-able output.

AttackBox Terminal

![[Pasted image 20250824220207.png]]


## Conclusion

In this room, we learned how to use Nmap to discover live hosts on any network. We also explored the common types of port scans and how we can use Nmap to find service version numbers. We also learned how to control the timing of the scan, and finally, we covered the different formats for saving Nmap scan results.

It is worth noting that it is best to run Nmap with `sudo` privileges so that we can make use of all its features. Running Nmap with local user privileges will still work; however, you should expect many features to be unavailable. You get a minimal portion of Nmap’s power when running it as a local user. For instance, Nmap would automatically use SYN scan (`-sS`) if you are running it with `sudo` privileges and will default to connect scan (`-sT`) if run as a local user. The reason is that crafting certain packets, such as sending a TCP SYN packet, requires root privileges.

Nmap is a very rich tool, and we only covered the most common and essential features in this room. In the [Network Security](https://tryhackme.com/module/network-security) module, four rooms are dedicated exclusively to Nmap. The table below lists most of the options we explained in this room to help you review and remember them.

| Option                                                              | Explanation                                                                                        |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `-sL`                                                               | List scan – list targets without scanning                                                          |
| **_Host Discovery_**                                                |                                                                                                    |
| `-sn`                                                               | Ping scan – host discovery only                                                                    |
| **_Port Scanning_**                                                 |                                                                                                    |
| `-sT`                                                               | TCP connect scan – complete three-way handshake                                                    |
| `-sS`                                                               | TCP SYN – only first step of the three-way handshake                                               |
| `-sU`                                                               | UDP Scan                                                                                           |
| `-F`                                                                | Fast mode – scans the 100 most common ports                                                        |
| `-p[range]`                                                         | Specifies a range of port numbers – `-p-` scans all the ports                                      |
| `-Pn`                                                               | Treat all hosts as online – scan hosts that appear to be down                                      |
| **_Service Detection_**                                             |                                                                                                    |
| `-O`                                                                | OS detection                                                                                       |
| `-sV`                                                               | Service version detection                                                                          |
| `-A`                                                                | OS detection, version detection, and other additions                                               |
| **_Timing_**                                                        |                                                                                                    |
| `-T<0-5>`                                                           | Timing template – paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5) |
| `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>` | Minimum and maximum number of parallel probes                                                      |
| `--min-rate <number>` and `--max-rate <number>`                     | Minimum and maximum rate (packets/second)                                                          |
| `--host-timeout`                                                    | Maximum amount of time to wait for a target host                                                   |
| **_Real-time output_**                                              |                                                                                                    |
| `-v`                                                                | Verbosity level – for example, `-vv` and `-v4`                                                     |
| `-d`                                                                | Debugging level – for example `-d` and `-d9`                                                       |
| **_Report_**                                                        |                                                                                                    |
| `-oN <filename>`                                                    | Normal output                                                                                      |
| `-oX <filename>`                                                    | XML output                                                                                         |
| `-oG <filename>`                                                    | `grep`-able output                                                                                 |
| `-oA <basename>`                                                    | Output in all major formats                                                                        |