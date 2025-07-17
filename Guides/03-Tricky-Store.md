# Guide: Tricky Store

`Tricky Store` is an advanced tool that handles a deeper level of security checks, particularly those related to hardware-level attestation.

### What it does

Play Integrity doesn't just check the software "fingerprint"; it also checks for hardware-level attestation. It asks the phone's secure hardware (the "Keystore" in the Trusted Execution Environment or TEE) to cryptographically sign a statement saying, "I am a genuine, untampered device with a locked bootloader."

Tricky Store intercepts this process. It fakes the response from the Keystore, providing a software-generated certificate that looks like it came from secure hardware. This is crucial for passing higher levels of integrity checks.

### How it works

The module name is a pun on "Keystore." It hooks into the key generation process. For the highest level of security (`MEETS_STRONG_INTEGRITY`), you can provide a `keybox.xml` file, which is a "donor" key from a real device. This allows Tricky Store to pass checks by using a real, un-revoked hardware key.
