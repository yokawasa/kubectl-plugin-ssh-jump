# Change Log

All notable changes to the "kubectl-plugin-ssh-jump" extension will be documented in this file.

## 0.8.0

- Support providing namespace and context by @partcyborg ([#23](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/23))


## 0.7.3

- Fix `Connection closed by remote host connection closed by unknown port 65535` issue ([#16](https://github.com/yokawasa/kubectl-plugin-ssh-jump/issues/16))
  - Add RSA workaround options (`-o HostkeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa`)to commands in ProxyCommand only if the local OpenSSH version >= `8.5`

## 0.7.2

- Fix `Bad configuration option: pubkeyacceptedalgorithms` issue ([#18](https://github.com/yokawasa/kubectl-plugin-ssh-jump/issues/18))
  - Add OpenSSH version check
  - Add RSA workaround options (`-o HostkeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa`) introduced in [ssh-jump-0.7.1](https://github.com/yokawasa/kubectl-plugin-ssh-jump/releases/tag/0.7.1) only if the local OpenSSH version >= `8.5`
- Add verbose option (`-v|--verbose`)

## 0.7.1

- Fix `root@127.0.0.1: Permission denied (publickey)` issue ([#13](https://github.com/yokawasa/kubectl-plugin-ssh-jump/issues/13))
  - Add options like `-o HostkeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa` which works for newer ssh client (`OpenSSH 8.5+`) scenario

## 0.7.0

- Support specifying a custom sshjump pod template by @partcyborg ([#14](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/14))

## 0.6.0

- Support SSH local port forwarding to access a remote server. This allows to forward the traffic form local machine to SSH jump then SSH jump will forward the traffic to the remote server.

## 0.5.0

- Fix to address pod sshjump pod scheduling on hybrid clusters ([#9](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/9), thanks to @swgriffith )

## 0.4.0

- Support PEM (Privacy Enhanced Mail) scenario where you create key-pair but you only have .pem / private key (downloaded from AWS, for example) and you don't have the public key on your side.

## 0.3.2

- Changed a validation for destination name to support valid characters of hostname for SSH destination node that can start from ASCII letters 'a' through 'z' (in a case-insensitive manner), the digits '0' through '9', or the hyphen ('-'). Ref [RFC952](https://tools.ietf.org/html/rfc952) for valid characters of hostname.
- Add Internal-IP info, not only hostname for node info in running get-node-list

## 0.3.1

- fixed typo: missing char ( [#3](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/3), thanks to @iuryfukuda )

## 0.3.0

- Added Args param to exec in ssh session ( [#2](https://github.com/yokawasa/kubectl-plugin-ssh-jump/pull/2), thanks to @iuryfukuda )
## 0.2.0

- Added -P|--port options for specifing SSH port that target node is listening (default 22)
- Added -o "StrictHostKeyChecking=no" for ssh login options 
- Changed the way to SSH login via SSH Jump Pod from using "-J" to using "ProxyCommand"
## 0.1.0

- Initial release (alpha release)
