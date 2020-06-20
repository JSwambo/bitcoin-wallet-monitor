# bitcoin-wallet-monitor
A distributed, rapidly deployable, self-managed monitor and response system for bitcoin wallets.

## Motivation
Custody is fundamental to all Bitcoin operations and so tools are needed to better enable individuals, businesses and other organizations to securely manage and protect their funds. As custody protocols develop from basic principles of key-management and recovery to security solutions that offer *defense in-depth* (no single point of failure) and enforce multiple independent difficulty bariers on adversaries, the requirements for monitoring and responding to events increases. A wallet owner should be automatically notified when events occur related to their funds. A wallet owner should be able to define response policies for particular events. 

Consider the example of [vault-custody](https://arxiv.org/abs/2005.11776). Here, the transfer of control of funds is highly restricted by enforcing a vault covenant that stipulates that funds can only be moved to either a hot wallet after the expiration of a time-lock, or to an emergency distributed deep cold wallet. The time-lock enables a delay-period where a wallet owner can respond to detected intrusions. The security of this *requires* a secure functioning wallet monitor and response system. 

## Design Questions

Is it necessary for the monitor to operate a full bitcoin-core node?
  - Maximum security by minimised trust
  - What are the lower bounds of performance a machine needs to reliably operate a full node?

What methods are available for rapid deployment across diverse hardware and operating systems?
  - Containerisation, virtualisation, rust + WASM?
  - [Bitcoin-Standup](https://github.com/BlockchainCommons/Bitcoin-Standup)
  
How to specify an API for handling arbitrary monitoring and response policies?

How to ensure reliable connectivity to wallet owner, across multiple independent communications channels?

Some desirable features:
  - Dead-man switch recovery
  - Tor hidden service
  - Distributed security: consistency and liveness checks among wallet monitor nodes
  - Distriuted Custody of (partially) pre-signed transactions for recovery and response
  
## Security Analysis

### 1. What assets need to be protected?

Ultimately, the funds controlled by the wallet and identifying information that links those funds to the wallet owner. Access to and control of the wallet monitor. Assets stored by the wallet monitor; address information, response policies, pre-signed transactions, ...

### 2. What are the risks to those assets?

Theft, loss of privacy, (D)DoS, ...

### 3. How well do the security solutions mitigate those risks?

...

### 4. What other risks does the security solution cause?

...

### 5. What trade-offs does the security solution require?

...

## Related Projects
https://arxiv.org/abs/2005.11776
https://github.com/re-vault/revault-demo
https://github.com/sr-gi/bolt13/blob/master/13-watchtowers.md
https://github.com/talaia-labs/python-teos
https://www.youtube.com/watch?v=Vkq9CVxMclE
https://github.com/commerceblock/coordinator
https://github.com/LightningPeach/watchtower
https://github.com/NSkelsey/watchtower
https://github.com/btcontract/olympus
https://link.springer.com/book/10.1007/978-3-642-24474-2
https://www.oreilly.com/library/view/applied-network-security/9780124172081/
https://www.wiley.com/en-gb/Advanced+Penetration+Testing:+Hacking+the+World%27s+Most+Secure+Networks-p-9781119367680






