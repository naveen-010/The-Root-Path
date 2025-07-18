# Tutorial: How to Fix STRONG Play Integrity

This guide provides the steps to pass the `MEETS_STRONG_INTEGRITY` check.

### Required Modules

*   A working root manager (e.g., KernelSU, Magisk)
*   ReZygisk (or Zygisk Next)
*   Play Integrity Fork (PIF)
*   Tricky Store
*   Tricky Store Addon

### Step-by-Step Instructions

1.  **Preparation:**
    *   Go to your ROM settings and disable any built-in Play Integrity spoofing options.
    *   If using Magisk, open Magisk settings, disable Zygisk and enforce DenyList. Reboot your device. (This is to ensure no conflicts).

2.  **Flash Core Modules:**
    *   Open your root manager app (e.g., KernelSU).
    *   Flash the modules in this specific order:
        1.  Flash `ReZygisk`. 
        2.  Flash `Play Integrity Fork`.
        3.  Flash `Tricky Store`.
        4.  Flash the `Tricky Addon` module.
        5.  Reboot

4.  **Configure PIF:**
    *   After rebooting, tap on the "Action" button in the notification to run its configuration. Close it when done.

5.  **Configure Tricky Store:**
    *   Tap on the "Action" button.
    *   In the Tricky Store configuration app:
        *   Tap the three-dot menu in the top right and choose **Select all apps**.
        *   Tap the three-dot menu and choose Deselect Unnecesary apps.
        *   Tap **Set Valid Keybox**.
        *   Tap **Set Security Patch**:
            *   Enable the **advanced** toggle.
            *   Click **Get security patch**.
            *   Wait for the "Done" pop-up to appear.
            *   Click **Save**.
        *   Click the final **Save** button at the bottom.
        *   Close the Tricky Store app from your recents screen.

Your Play Integrity should now be fixed and passing the strong check. 
