[![](media/project_dark_home.png)](documentation.md)

# QR code

QR codes can be made using the Python package `pyqrcode`.

## setup

```Bash
git clone https://github.com/mnooner256/pyqrcode.git
cd pyqrcode
python
```

## example

```Python
import pyqrcode
qr = pyqrcode.create("my key text")
qr.png("key_public.png", scale = 50)
```

## URI

```
otpauth://totp/Example:alice@google.com?secret=JBSWY3DPEHPK3PXP&issuer=Example
```

```
otpauth://TYPE/LABEL?PARAMETERS
```

```
otpauth://TYPE/GENERALSOLUTIONS?secret=0123456789
```

```Python
import pyqrcode
qr = pyqrcode.create("otpauth://TYPE/GENERALSOLUTIONS?secret=0123456789")
qr.png("secret.png", scale = 50)
```
