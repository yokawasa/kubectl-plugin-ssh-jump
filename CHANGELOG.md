# Change Log

All notable changes to the "kubectl-plugin-ssh-jump" extension will be documented in this file.

## 0.3.1
- fixed typo: missing char ( [PR#3](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/3), thanks to @iuryfukuda )

## 0.3.0
- Added Args param to exec in ssh session ( [PR#2](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/2), thanks to @iuryfukuda )

## 0.2.0
- Added -P|--port options for specifing SSH port that target node is listening (default 22)
- Added -o "StrictHostKeyChecking=no" for ssh login options 
- Changed the way to SSH login via SSH Jump Pod from using "-J" to using "ProxyCommand"


## 0.1.0
- Initial release (alpha release)
