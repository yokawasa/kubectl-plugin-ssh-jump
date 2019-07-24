# Change Log

All notable changes to the "kubectl-plugin-ssh-jump" extension will be documented in this file.

## 0.2.0
- Added -P|--port options for specifing SSH port that target node is listening (default 22)
- Added -o "StrictHostKeyChecking=no" for ssh login options 
- Changed the way to SSH login via SSH Jump Pod from using "-J" to using "ProxyCommand"


## 0.1.0
- Initial release (alpha release)
