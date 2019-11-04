[![](media/project_dark_home.png)](documentation.md)

# PGP

## terminal PGP (ok, but awkward)

### Generate key.

```Bash
gpg --gen-key
```

- Select `(1) RSA and RSA (default)`.
- Select keysize 2048.
- Set indefinite expiry time (0, y).
- Set user details.
- Generate entropy.
- Record the key identifier and fingerprint.
- Back up `/home/"${USER}"/.gnupg/trustdb.gpg`.
- Create an ASCII armoured version of the public key.

Set the variable `GPGKEY` to your GPG key.

```Bash
gpg --output key_public.asc --export -a ${GPGKEY}
```

- An ASCII version of the private key can be created. This should be done with care.

```Bash
gpg --output key_private.asc --export-secret-key -a ${GPGKEY}
```

- The public and private keys can be imported on another computer. This should be done with care.

```Bash
gpg --import key_public.asc
gpg --import key_private.asc
```

### Send encrypted messages.

- Get the recipient's public key and USER-ID string and import it to the local PGP public key ring.

```Bash
gpg --import public_key.asc
```

- Create a secret message in a text file and encrypt it using the USER-ID string.

```Bash
echo "This is top secret." > secret_message.txt
gpg --encrypt --armor -u <ID of sender> -r <ID of receiver public key> secret_message.txt
```

- Send the encrypted file `secret_message.txt.asc`.

### Receive encrypted messages.

Save a file that has been encrypted using your public key (e.g. secret_message.txt.gpg).

```Bash
gpg --decrypt secret_message.txt.gpg > secret_message_decrypted.txt
```

- Enter the passcode for the private key.

## GUIs

- [bochica](https://github.com/wdbm/bochica)
- GNU Privacy Assistant (`sudo apt install gpa`)
- Thunderbird PGP (`sudo apt install enigmail`)
