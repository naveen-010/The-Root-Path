# Guide: How It All Works Together

Here is a step-by-step scenario of how these modules work in concert to allow a sensitive app to run on a rooted device.

1.  **You open your banking app.**
2.  The app requests a Play Integrity check from Google Play Services to ensure the device is secure.
3.  As the Google Play Services process starts its checks, **ReZygisk** loads your Zygisk modules into its memory.
4.  **NoHello** immediately gets to work, unmounting any traces of `/data/adb/ksu` or other module paths so that the Google process can't see them.
5.  Google Play Services asks the system for the device's identity (its fingerprint). **Play Integrity Fork** intercepts this and provides the fingerprint of a certified Google Pixel phone.
6.  Google Play Services asks the Keystore for a hardware-backed certificate to prove the bootloader is locked. **Tricky Store** intercepts this and provides its own fake (but valid-looking) certificate.
7.  The Google process, having been fed false information at every critical step, believes your phone is a genuine, non-rooted device.
8.  It reports a "PASS" verdict back to your banking app.
9.  **The banking app lets you log in.**
