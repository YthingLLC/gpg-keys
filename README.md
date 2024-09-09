# Ything LLC GPG Keys

This repository contains all valid GPG keys for Ything LLC. 

Keys that are no longer valid / expired will eventually be placed into an archive folder within
this repository.

Any signature from any of these keys should be considered valid unless the key has been revoked / disavowed.

## Key Definitions

y5nfc-* keys: These keys are generated in hardware on [Yubikey 5 NFC](https://www.yubico.com/product/yubikey-5-series/yubikey-5c-nfc/)
security keys. These secret keys exist only in the Yubikey hardware itself, and is protected via a pin.

The secret keys are protected by a PIN. If the PIN is entered incorrectly more than 3 times,
yubikey will refuse to provide signatures with the associated key. This can be extended with the PUK PIN
that is also set on the Yubikeys. If this is entered wrong 3 times it will then lock the Yubikey where only
the Admin PIN can then be used to unblock signatures. 

If the Admin PIN is also input incorrectly 3 times this will, permanently, and irrecoverablly, cause loss
of the keys stored within the Yubikey. It will no longer be possible for the GPG keys to be used, and only
new GPG keys can be generated on the Yubikey. 

This ensures that the keys generated by the Yubikey are very secure, while also providing a high level of
usability. The secret keys are never known by the computer that is requesting signatures. 

This does not mean that Yubikeys are absolutely infallible, Yubico issued a [security advisory](https://www.yubico.com/support/security-advisories/ysa-2024-03/)
about a potential side channel attack that would allow for secret key recovery; however, as detailed 
out in the security advisory, as well as by [Ars Technica](https://arstechnica.com/security/2024/09/yubikeys-are-vulnerable-to-cloning-attacks-thanks-to-newly-discovered-side-channel/),
the exploit requires physical posession of the Yubikey, knowledge of the PINs, as well as destructive
entry into each Yubikey. A potential attacker would need to have possession of the physical Yubikey
for "10 hours," remove the case of the Yubikey, replace the case, and return the key, all without
the owner of the key having knowledge of this being done. 

Due to the sophisticated nature of the above mentioned exploit, and the additional security provided
by only storing the secret keys on the Yubikeys themselves, Ything LLC considers these to be the most
secure GPG keys available. 

As an additional level of assurance, using Yubico's software, the ability to use PIV / GPG via NFC
has been disabled on the Yubikeys associated with these GPG keys.

Future GPG Smartcard devices may be considered in the future.

Ything LLC does not have a reason to believe that the hardware used by Yubikey is "untrustworthy"
any more than other proprietary encryption devices. (Yes, the firmware running on them is closed source!)

mbook.pub: This key is a traditional software GPG key; however, an exportable certification by
one of the yubikeys was applied to this key (and can naturally, be revoked in the future); and,
it is encrypted with a strong password; and, it is also stored on a drive encrypted with [FileVault 2](https://en.wikipedia.org/wiki/FileVault),
that **can not** be unlocked by iCloud. 

This key was generated on an Apple MacBook Pro - Nov 2023. Apple Silicon computers have been described
by the Asahi Linux Team as "[the most secure general purpose computers available to the public](https://github.com/AsahiLinux/docs/wiki/Introduction-to-Apple-Silicon/d208e73a92084b210d7c9033aa69be782287bd54)".

Given the above, Ything LLC is reasonably certain that GPG keys stored on an Apple Silicon computer
with FileVault full disk encryption enabled can be considered reasonably secure; however, given that
keys that are not subject to hardware protection by a PIN are natually weaker, this key is not as trusted
as a key generated by a physical security key. Yes, the full disk encryption by FileVault *is* protected
by a hardware security module, Apple's [Secure Enclave Processor](https://support.apple.com/guide/security/secure-enclave-sec59b0b31ff/web); however,
it's not designed for protection of GPG keys in particular. The GPG key itself, while encrypted, is
still stored on block device as an ordinary file. It is on an encrypted filesystem, but it is still
an ordinary file, and it is possible for this file to be copied to other systems.

At the time of this writing, Ything LLC has no reason to believe that a copy of this key, encrypted,
or otherwise, has been made. It is impossible to to provide the same level of assurance that this key
will not be copied as provided by a Yubikey. This does not mean that simply "copying" the file
will provide access to the secret key, the file that contains the secret key *is* encrypted by GPG; however,
it does mean that a particularly skilled attacker *may* have an easier time breaking this key as unknown
physical posession is not required, and there is no brute force protection for keys stored as files.

Ything LLC does not have a reason to believe that FileVault, or Apple's Secure Enclave Processor are
"untrustworthy" any more than other proprietary encryption software or devices; but, trust in this key
is naturally predicated on more entities requiring "trust" than a Yubikey.


## End Note

As Ything LLC is not currently aware of any solutions that provide a higher level of assurance, without
requiring trust of additional entities, Ything LLC believes that the security and protection of the
secret GPG keys is achieved. Given the expected reputational damage that Apple or Yubico would experience
from the public discovery of a backdoor into their products that allows for secrets to be duplicated,
Ything LLC has no reason to believe that a higher security solution is publicly available.

Other solutions that exist (such as the Nitrokey) require Ything LLC to use a far less widely used
encryption product / software. This does not mean that such products are "guaranteed" to be exploitable;
however, it does mean that there are less "eyeballs" on such things. Ything LLC also agrees with Yubico's
stance on lack of firmware upgradability. By allowing firmware to be upgraded, it opens up a potential
attack vector in a malicious firmware "upgrade."

Ything LLC is not aware of *any* available solution that is as widely deployed, and marketed by 
companies with a high reputation for security / trustworthiness. If you are aware of a potential
solution that does not require a compromise not previously addressed, I'd love to hear about it!
