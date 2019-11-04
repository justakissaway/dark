[![](media/project_dark_home.png)](documentation.md)

# 2-factor authentication (2FA) 2016-07-21T1233Z

There are two major 2FA schemes in general use today. One involves the login provider sending an SMS code and that is used to log in. The other is Time-based One-Time Password (TOTP) algorithm. TOTP is an algorithm that computes a one-time passcode from a shared secret key and the current time and is adopted in [RFC 6238](https://tools.ietf.org/html/rfc6238). It combines the secret key with the current timestamp using a cryptographic hash function (default: Secure Hash Algorithm 1 (SHA-1)) to generate a one-time passcode (OTP). The timestamp typically increases in 30-second intervals.

The typical approach in TOTP is as follows. A user enters a username and a passcode into a website or other server, generates a one-time passcode using TOTP running locally on a smartphone or other device and enters that passcode into the server aswell. The server then also runs TOTP to verify the entered one-time passcoce. For this to work, the clocks of the user's local device and the server should be roughly synchronised (and the server is likely to accept OTPs around a certain time deviation from the user's timestamp. A single, secret key, to be used for all subsequent authentication sessions must have been shared between the server and the user's device over a secure channel ahead of time. With further steps, the user can also authenticate the server using TOTP.

Google Authenticator (which you should not use for reasons explained later) is an example of TOTP. When it is set up on a Google account, Google shares a secret passcode with the user which gets stored on the user's device. A hash of that code with the current time can be compared with a hash of Google's copy of the secret passcode with the current time for authentication. No internet access is required to get a valid authentication hash.

## desktop applications for 2FA

### che_guevara_otp

- <https://github.com/wdbm/che_guevara_otp>

## phone applications for 2FA

### andOTP

- [F-Droid](https://f-droid.org/en/packages/org.shadowice.flocke.andotp)
- [GitHub](https://github.com/andOTP/andOTP)

### Google Authenticator

Note that only early versions (up to version 2.2.1 inclusive) of Google Authenticator should be used because it suddenly changed from being open source to closed source, which is suspicious and indicative of a backdoor in the closed source version. A fork of the open source version is available [here](https://github.com/google/google-authenticator). The application andOTP, mentioned earlier, is strongly recommended instead.

- Go to the Google 2-step vertification page.
- Under the Authenticator app field, select to edit.
- Select to change (not remove?).
- Access Authenticator on the local device and select to set up an account.
- The barcode can be scanned, but it might be preferable to enter the key directly (and to store it securely).
