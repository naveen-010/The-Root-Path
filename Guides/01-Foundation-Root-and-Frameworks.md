# Guide: The Foundation - Root and Frameworks

These modules provide the basic structure for all your other modifications to work. Let's break down the essential components.

### 1. Root Provider (e.g., KernelSU)

*   **What it is:** This is your root solution. KernelSU is a modern method that integrates root capabilities directly into your phone's kernel (the core of the operating system).
*   **Why it matters:** This approach can sometimes be harder for apps to detect compared to traditional root methods.

### 2. Zygisk

*   **What it is:** The "Zygote" process is one of the first processes to start on an Android device and is the parent of all application processes. Zygisk is a framework that allows your root manager (and the modules you install) to run code directly inside every app's process as it starts.
*   **Why it matters:** This is incredibly powerful for making modifications that affect the entire system or specific apps at runtime.

### 3. ReZygisk / Zygisk Next

*   **What it is:** Since KernelSU doesn't have Zygisk built-in (like Magisk does), `ReZygisk` or `Zygisk Next` acts as a compatibility layer.
*   **Why it matters:** It creates a Zygisk environment on your KernelSU-rooted device, allowing you to use powerful Zygisk modules.

### 4. LSPosed (Xposed Framework)

*   **What it is:** LSPosed is a framework that allows you to run "Xposed Modules." Think of it as a platform that other, more specific mods can plug into. It uses the Zygisk framework to load itself into every app process.
*   **Why it matters:** You can use LSPosed for a huge variety of mods, including UI customizations, advanced ad-blocking, or other app-specific tweaks that require deep integration.
