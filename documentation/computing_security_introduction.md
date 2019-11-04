[![](media/project_dark_home.png)](documentation.md)

![](media/Do_WdsQUYAIDIv0.jpg)

# general guidelines and terminology for computing security

Economics migrates to different forms. Slavery in the USA migrated to exploitation, the like of which is seen in for-profit prisons. The power of states used to be resources, mainly land, but this is briskly migrating to information; the flow of information, the use of information to learn about the world and to manipulate people. Information trumps weapons if it is sufficiently deep. Decentralization of the state and of control of information is likely essential to preventing future oppression.

## essential features for security

### don't trust; verify

Never simply trust security claims. Always require mathematically-verifiable ways of verifying claims. An example of this is performing a checksum on a downloaded precompiled program.

- <https://protonmail.com/security-details>

### open source

This is like peer-review in science. "Audited" (terminology used by Apple, Threema and the like) is not enough because cherry-picked security researchers is not enough. The eyes of all of the world's security researchers must be able to see the code and to verify claims, security and the like.

Open source does not imply security, but it is the bare minimum needed to be able to verify security or to fix bugs.

### zero access encryption

This means that the remote service you are using stores only encrypted data.

- <https://protonmail.com/blog/zero-access-encryption>

### end-to-end encryption (E2EE)

This means that in communicating, data being sent is encrypted by the sender, then the encrypted data is actually sent, then the received encrypted data is decrypted by the receiver.

- <https://protonmail.com/blog/what-is-end-to-end-encryption>

If an E2EE service is cracked, the crackers don't have access to your data. E2EE is good for democracy. E2EE protects free speech and privacy, shields persecuted activists, dissidents and journalists from intimidation and oppression.

## essential features for computing freedom

### user essential computing freedoms

- <https://www.gnu.org/philosophy/free-sw.html>
- <https://www.gnu.org/philosophy/free-software-even-more-important.html>
- <https://www.ted.com/talks/andy_yen_think_your_email_s_private_think_again>

### libre software and hardware, FOSS

- <https://www.gnu.org/philosophy/floss-and-foss.en.html>

### force of protection, e.g. law

- <https://protonmail.com/blog/gdpr-email-compliance>

![](media/Google.png)

# anonymity and privacy online

![](media/A7fWSL0.jpg)

In order to surf the web anonymously, there are a few options. The most common and reliable methods are Tor (The Onion Router) and VPN (Virtual Private Network) services. Both methods allow one to hide one's IP address and location so that it is difficult for someone to track one's online activities. Both of these approaches allow one to bypass internet censorship and georestricted sites.

Tor works by routing internet traffic through Tor's network of pseudorandomly-selected relays (run by volunteers) that are scattered all over the world. All the traffic that passes through the relays within the Tor network gets encrypted and reencrypted multiple times until it reaches the exit node (the last computer in the Tor network). At the exit node, the last layer of encryption gets decrypted and the data is sent to the destination without revealing who the sender is. Each of the nodes can see only the data and the IP address of the node in front and the node behind it. So, in principle, no one can find out the complete path between the local computer and the website to which it is connected at any point. In addition, each completed path is good for only 10 minutes and then new random paths are generated.

This impedes ISPs etc. from knowing which websites are visited. Further, the websites visited do not know the IP address of the local computer, only the IP address of the computer at the exit node. The strength of Tor is in the number of relay volunteers. The more volunteers there are, the stronger the security of the whole Tor network becomes.

A VPN service protects privacy by masking the IP address and encrypting internet traffic. A VPN server acts as a proxy to connect to a desired website on the behalf on the local user. The website sees the IP address of the VPN server, not the local computer. Further, all internet traffic is encrypted. What is visible to the ISP and network operator is that an encrypted connection is being made. VPNs are generally not blocked by ISPs because they are commonly used by remote workers to connect to their company's networks.

Tor impedes tracing the sites visited by a user to the user IP address. Since the network is distributed, it is extremely difficult for a government or organisation to shut it down. Tor is slow because the data is routed through a number of relays, so it is not recommended for browsing or streaming georestricted video content. Some ISPs actively search out and block Tor relays, making it difficult for some users to connect. Since exit node traffic is unencrypted, anyone (police, governments, hackers etc.) that is running the exit node can see the internet traffic. Further, anyone can set up a Tor exit node and there is nothing to prevent that person from spying on users. So, in order to send sensitive information, use secure websites (HTTPS).

VPN connection speed is a lot faster than Tor because there is only the VPN server that stands between the local computer and the requested site. VPN provides better privacy and security than Tor.

VPN provides *privacy* rather than anonymity and requires the local user to trust the VPN provider. This is because, should it wish to or is compelled to, the VPN provider can see what the user does online.

- <https://old.reddit.com/r/unitedkingdom/comments/avcqm7/is_it_time_to_use_vpn_every_day>

## Tor through VPN

In this configuration, first there is a connection to the VPN server and then to the Tor network before accessing the internet. This means that it is not apparent to the ISP that Tor is being used, though it can know that a VPN is being used. The Tor entry node does not see the local IP address, but the IP address of the VPN server. A no-logs VPN provider can provide additional layers of security. The VPN provider knows the local IP address. Tor exit nodes are often blocked.

## VPN through Tor

In this configuration, the VPN client works with Tor. AirVPN and BolehVPN work with Tor. The apparent IP address on the internet is that of the VPN server. Because of connection to the VPN server through Tor, the VPN provider cannot see the local IP address, only that of the Tor exit node. When combined with an anonymous payment such as Monero or tumbled Bitcoins made anonymously over Tor, this means that the VPN provider has no obvious way to identify the user, even if it kept logs. There is protection from malicious Tor exit nodes, as data is encrypted by the VPN client before entering and exiting the Tor network, though while the data is encrypted, the ISP will be able to see that it is heading towards a Tor node. It bypasses blocks on Tor exit nodes. It allows one to choose the server location which is useful for geospoofing. All internet traffic is routed through Tor, even by programs that do not usually support it. The VPN provider can see the traffic but has no obvious way to connect it to you. This configuration is usually regarded as fairly secure because it promoted complete and true anonymity. In order to maintain anonymity, the user must always connect to the VPN through Tor (if using AirVPN or BolehVPN, this is performed automatically once the client has been configured correctly).

Some good VPN services are as follows:

- [AirVPN](https://github.com/wdbm/resources_AirVPN)
- [NordVPN](https://nordvpn.com/bigmoney) (link to deal -- 3 years for 99 USD, 2018-07)

## Tor

![](media/2018-10-11T1128Z_Tor.png)

### setup

```Bash
wget https://www.torproject.org/dist/torbrowser/7.5.4/tor-browser-linux64-7.5.4_en-US.tar.xz
dtrx tor-browser-linux64-7.5.4_en-US.tar.xz
```

- Acquire VPN access.
    - [VPN comparison](https://www.deepdotweb.com/vpn-comparison-chart/)
    - IPVanish
- Close communications programs and websites (e.g. Skype, Dropbox, Google Drive, Facebook) to combat location leaks.
- Access VPN.
- Launch Tor.
- Disable JavaScript.
    - <about:config>
    - `javascript.enabled`: false

Screenshots are possible in standard Firefox using [Firefox Screenshots](https://screenshots.firefox.com) and GCLI, by pressing `Shift` `F2` and then entering a command like `screenshot --fullpage 2018-05-31T1725Z.png`. This functionality is not (yet?) available in Tor.

### errors

If the keyboard is not working in Tor, you may need to run the following:

```Bash
killall ibus-x11
```

### Orbot (Android proxy with Tor)

- <https://play.google.com/store/apps/details?id=org.torproject.android>

### Orfox (browser for Orbot)

- <https://play.google.com/store/apps/details?id=info.guardianproject.orfox>

### Guardian Project

- <https://guardianproject.info/apps>

## PEBCAW

[PEBCAW](https://github.com/wdbm/pebcaw) (Problem Exists Between Computer And World) monitors internet connection security by comparing the observed IP with a whitelist of VPN and Tor IPs. It notifies if the IP is not in the whitelist, and optionally can notify if the IP is in a SIGINT country, and optionally can display IP details continuously.

# generate internet noise

It is possible that setting a computer or phone loading pseudorandom sites passively provides some privacy from modelling and some legal protection, but mostly it should be viewed as a digital protest.

## Internet Noise

- <http://makeinternetnoise.com>

## Squawk

- <https://squawk.cc>

Squawk can be deployed by adding the following code to a web page:

```HTML
<script src="https://squawk.cc/squawk.js"></script>
```

This causes web site visitors to make a single request to a pseudorandom IP address, for every request that is served with the script tag. This adds some noise to logs being kept by ISPs.

## Noisy

Noisy is a Python script that generates pseudorandom HTTP/DNS traffic noise.

- <https://null-byte.wonderhowto.com/how-to/flood-your-isp-with-random-noisy-data-protect-your-privacy-internet-0186193>
- <https://github.com/1tayH/noisy>

# MAC addresses

A valid MAC address can be generated in the following way:

```Python
import random
print("{aa:02x}:{bb:02x}:{cc:02x}:{dd:02x}:{ee:02x}:{ff:02x}".format(
    aa = random.randint(0, 255),
    bb = random.randint(0, 255),
    cc = random.randint(0, 255),
    dd = random.randint(0, 255),
    ee = random.randint(0, 255),
    ff = random.randint(0, 255)
))
```

Get the list of names of network devices:

```Bash
ls /sys/class/net

docker0  enx3c18a0000516  lo  wlp4s0
```

Get the status of the network devices:

```Bash
>ip -o link show | awk '{print $2,$9}'

lo: UNKNOWN
wlp4s0: UP
docker0: DOWN
enx3c18a0000516: UP
```

Get the status of the network devices:

```Bash
>nmcli dev status
DEVICE           TYPE      STATE         CONNECTION 
docker0          bridge    connected     docker0    
wlp4s0           wifi      connected     KELVIN     
enx3c18a0000516  ethernet  disconnected  --         
lo               loopback  unmanaged     -- 
```

Spoof/change a MAC address:

```Bash
sudo service network-manager start
sudo ifconfig wlp4s0 down
sudo macchanger --mac 28:27:c4:f6:ca:a5 wlp4s0
sudo ifconfig wlp4s0 up
sudo service network-manager stop
```

# proxies

## set up a server to provide an internet connection via SSH and SOCKS

SSH to the server.

```Bash
ssh -D1080 -oControlMaster=no wbm@ppelx.physics.gla.ac.uk
```

Set up Firefox.

- Edit > Preferences > Network > Connection > Settings...
- Instead of "No proxy", select "Manual proxy configuration:".
- SOCKS Host: 127.0.0.1 Port: 1080

## web proxies

###  U.S. web proxies

- 107.20.64.7:3128 (2013-08-13 working, slow)

### youtube-dl proxies

- example: download a YouTube video that is not geoblocked in the U.S.

```Bash
http_proxy='72.64.146.135:8080' youtube-dl http://www.youtube.com/watch?v=yo0eDetRLV4
```

## sshuttle: where transparent proxy meets VPN meets ssh

sshuttle is a transparent proxy server that works as a poor VPN. It forwards over SSH, does not require administrator privileges, supports DNS tunnelling and works with GNU/Linux and MacOS.

### setup

```Bash
sudo pip install sshuttle
```

### usage

```Bash
sudo sshuttle -r user@www.example.org:8080 0/0
nc -vvv 127.0.0.1 1080
```

# mitigating printer identification microdots

- <https://tu-dresden.de/ing/informatik/sya/ps/die-professur/news/geheime-daten-auf-dem-druckpapier-diplominformatiker-der-tu-dresden-entwickeln-verfahren-gegen-druckerueberwachung>
- <https://github.com/dfd-tud/deda>

### references

- [privacytools.io](https://privacytoolsio.github.io/privacytools.io/)
- [privacy by creating noisy data](https://www.reddit.com/r/privacy/comments/93n2ci/instead_of_preventing_fb_and_google_from_tracking)
- [Online Security Guide for Journalists -- ProtonMail](https://protonmail.com/blog/journalist-online-security-tips)
- [How I Fully Quit Google (and you can too) -- Nithin Coca](https://medium.com/@excinit/how-i-fully-quit-google-and-you-can-too-4c2f3f85793a)
- [NSA Prism program taps in to user data of Apple, Google and others](https://www.theguardian.com/world/2013/jun/06/us-tech-giants-nsa-data)
