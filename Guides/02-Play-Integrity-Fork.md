# Guide: Play Integrity Fork (PIF)

`Play Integrity Fork` (PIF) is your primary tool for passing the `MEETS_DEVICE_INTEGRITY` check, which is a basic part of Google's Play Integrity API.

### What it does

PIF works by spoofing your device's "fingerprint." When an app checks for your device's identity, PIF intercepts the request. Instead of replying with your phone's true identity (which would fail the check on a modified device), it provides the fingerprint of a different, trusted device (usually a Google Pixel phone) that is known to pass Play Integrity.

### How it works

The module contains scripts (like `autopif2.sh`) that can automatically download the latest official firmware information for Google Pixel phones. This is done to extract "clean" fingerprints. The module's code then injects these fake values into the Google Play Services process when it's performing the integrity check, tricking it into thinking your device is an unmodified, certified phone.
