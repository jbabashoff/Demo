# Configure Git on Windows to use a proxy Server

This guide shows you how to configure Git on Windows behind a proxy server


## Installation

1. Download and run the [Git for Windows Client](https://git-scm.com/install/windows) installer
	* Install with the defaults including:
	
		* Git BASH
		* Gig Credential Manager



## Configure Git to use Git Credential Manager and Proxy

1. Configure Git Credential Manager Core

```bash

git config --global --unset credential.helper
git config --global credential.helper manager-core

```


2. Configure Git to use proxy server

```Bash

git config --global http.proxy http://www-proxy.adelaide.edu.au:3128
git config --global https.proxy http://www-proxy.adelaide.edu.au:3128


```

3. Enable Windows Integrated Authentication

```Bash

git config --global http.sslBackend schannel
git config --global http.proxyAuthMethod negotiate

```


## References

* [Use Git Credential Manager to authenticate to Azure Repos](https://learn.microsoft.com/en-us/azure/devops/repos/git/set-up-credential-managers?view=azure-devops)
* [git-credential-manager](https://github.com/git-ecosystem/git-credential-manager)
* [GCM-NTLM and Kerberos Authentication](https://github.com/git-ecosystem/git-credential-manager/blob/main/docs/ntlm-kerberos.md)
* [GCM-Network and HTTP configuration](https://github.com/git-ecosystem/git-credential-manager/blob/main/docs/netconfig.md)

