# Joystick Gremlin Whitelister
Automatically whitelists [Joystick Gremlin](https://github.com/WhiteMagic/JoystickGremlin) with [HidGuardian](https://github.com/ViGEm/HidGuardian), without the need for HidCerberus or for running Joystick Gremlin as administrator.

# Philosophy
- HidCerberus and my solution are both Windows services that run with elevated privileges. However HidCerberus presents an unauthenticated UI and API via local HTTP. Mine just listens for a known process starting/ending and alters the whitelist appropriately, then toggles a device to make sure Joystick Gremlin loads them.
- We want to be doing as little as possible with elevated privileges, so presenting an API unnecessarily is bad.
- Changes to which devices are to be hidden by HidGuardian are unlikely to be frequent, so presenting an API is unnecessary. It would be better to create a small application that requires elevated permissions that can be run in this infrequent scenario.

# Proof of Concept only
Feel free to use this code. I'm unsure if I want to polish it up more or release it yet.

# To-do list
- Installer
- Verify joystick_gremlin.exe process
  - Perhaps hash the file at install and store hash for checking at runtime?
- Allow basic configuration in case this is useful for other programs besides Joystick Gremlin
