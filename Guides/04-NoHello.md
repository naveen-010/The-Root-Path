# Guide: NoHello

While PIF and Tricky Store hide the *results* of being rooted, `NoHello` tries to hide the *presence* of the root tools themselves.

### What it does

NoHello's main job is to hide the root solution itself from detection. It does this by aggressively unmounting (detaching) any filesystem paths related to KernelSU, Magisk, or other modules from the process that is performing the security check. If the process can't see the files, it can't detect them.

### How it works

The name "NoHello" is a reference to hiding from detection ("hello world" is a common programming term). The module's code unmounts sensitive paths and "sanitizes" file descriptors to erase traces of their existence.

The message you see in your root manager's modules tab, "Nohello unmounted x times," is a log from this module telling you how many times it has successfully performed this hiding action since the last reboot.
