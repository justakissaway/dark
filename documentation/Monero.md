[![](media/project_dark_home.png)](documentation.md)

# Monero

Monero is a cryptocurrency created in 2014 that focuses on fungibility, privacy and decentralization. It uses an obfuscated public ledger that is designed such that users can send transactions but others cannot tell the source, amount or destination of a transaction. 

The symbols for Monero are XMR and ɱ.

For unlinkability, unlike Bitcoin, Monero funds are not associated to addresses. When funds are sent to a public address, the funds get sent to a randomly-generated one-time destination address (the "commitment public key"). So, rather than the sender public address or the recipient public address appearing in the public ledger, there is a stealth address that is visible to only the sender and receiver. When the recipient checks for funds, they need to check the blockchain to see if any funds are destined to them. The recipient has a secret view key which is used to check each transaction in the blockchain to see if it was addressed to them. Only those that have the secret view key can see the funds received by an address. This stealth address hides the address of the recipient. Untracability his involves ring signatures and the Peterson commitment formula. Internet traffic is hidden using Kovri.

# wallets

## Monerujo

- [F-Droid repository](https://f-droid.monerujo.io)
- [Google Play](https://play.google.com/store/apps/details?id=com.m2049r.xmrwallet)
- [GitHub](https://github.com/m2049r/xmrwallet)

The wallets are stored at the `monerujo` directory of the device internal storage.
