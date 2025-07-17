# Guide: Hide My Applist (HMA)

Think of your phone's security like getting into a high-security building.

*   **Play Integrity Check (The Front Door):** PIF and Tricky Store are your tools to show a fake ID and get past this first checkpoint.
*   **App List Scan (The Room Sweep):** Once you're inside, some high-security apps do an extra check. They look around the "room" (your phone) to see who else is there. If they see suspicious apps like "KernelSU Manager" or "LSPosed," they know something is up.

This is where `Hide My Applist` (HMA) comes in.

### What it does

HMA acts as a doorman for every app. When your banking app asks the Android system, "Hey, give me a list of all installed apps," HMA intercepts that request. It looks at a rulebook that you create and provides a modified, "clean" list to the banking app. The banking app never sees that you have KernelSU or LSPosed installed.

### How it Works

HMA is an LSPosed Module, meaning it uses the framework to inject itself into the `PackageManagerService` (PMS) – the master service that knows about every app on your phone. When one app (the caller) tries to get information about another app (the query), HMA's code runs and checks its rules. If the caller is a target (e.g., a banking app) and the query is on the hide list (e.g., KernelSU), HMA tells the system to pretend the queried app doesn't exist.

### How You Use It

The HMA app is your control panel for creating the rulebook.

*   **Blacklist (Recommended):** This is the easiest mode. You create a template (e.g., "Root Apps") and add apps like KernelSU Manager and LSPosed Manager to this list. Then, you select your banking app and apply the "Root Apps" template to it.
    *   **Result:** When your banking app asks for the app list, HMA will hide KernelSU and LSPosed from it.
*   **Whitelist:** This is the opposite and much stricter. You list only the handful of apps you want a target app to see. This can easily break apps and is not recommended unless you know exactly what you're doing.
