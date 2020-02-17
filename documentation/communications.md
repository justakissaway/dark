[![](media/project_dark_home.png)](documentation.md)

# secure communications

- Signal
- [Jitsi Meet](https://jitsi.org/jitsi-meet)
    - [run in browser](https://meet.jit.si)
    - [Android](https://play.google.com/store/apps/details?id=org.jitsi.meet)
- Matrix
- Tox
- [Ricochet](https://ricochet.im)

![](media/2018-10-14_Facebook_Portal.png)

# peer-to-peer mobile communications

## Briar peer-to-peer

- <https://briarproject.org>
- <https://f-droid.org/en/packages/org.briarproject.briar.android/>
- <https://play.google.com/store/apps/details?id=org.briarproject.briar.android>

## The Serval Mesh (probably not a reliable option)

- <https://play.google.com/store/apps/details?id=org.servalproject>

# SMS Privacy: telephone number SMS privacy and verification service

This is a hidden service by [_jstanley](https://www.reddit.com/user/_jstanley) (James Stanley) that provides anonymous phone numbers for texting in exchange for Bitcoin/Monero, which could be used for phone verification that is not linked to your identity. The service enables one to buy mobile phone numbers with a completely anonymous signup. One can then send and receive SMS text messages on these anonymous numbers using a web interface.

- <http://smspriv6fynj23u6.onion>
- <https://smsprivacy.org>

# file sharing

## Magic-Wormhole -- send a file easily and fairly securely from one computer to another

- <https://github.com/warner/magic-wormhole>

### setup

```Bash
pip install magic-wormhole
```

### usage

On the sending computer, run a command like `wormhole send file.pdf` and this should return a code that can be used on the receiving computer. On the receiving computer, run the command `wormhole receive` and this should accept the code.

## Firefox Send -- end-to-end encrypted file sharing

- <https://send.firefox.com>

## OnionShare

OnionShare launches a Tor web server, generating a URL to share that makes files of arbitrary size accessible.

```Bash
sudo add-apt-repository ppa:micahflee/ppa
sudo apt update
sudo apt install -y onionshare
```
