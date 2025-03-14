# Tron Wallet Features

## WalletConnect Support
[WalletConnect](https://walletguide.walletconnect.network/) is crafted to bridge the divide between cryptocurrency wallets and decentralized applications (dApps). It empowers users to connect their crypto wallets to numerous dApps either via a QR code or deep linking.

Currently only TokenPocket wallet support WalletConnect protocol well. In other wallet apps you may encounter some issues.

The following table shows the wallet support to WalletConnect protocol:

| Wallet | Connect to dApps | Message Signing | Transaction Signing 
|------|------|------|-----|
| TokenPocket | ✅  | ✅ | ✅ 
| Bitget | ✅ | ❌ | ❌ 
| Okex |  ❌ | ❌ | ❌ 
| Bybit |  ❌ | ❌ | ❌ 
| Trust |  ❌ | ❌ | ❌ 
| foxwallet |  ❌ | ❌ | ❌ 
| imToken |  ❌ | ❌ | ❌ 
| GateWallet |  ❌ | ❌ | ❌ 

## Tron Provider
According to [TIP-1193](https://github.com/tronprotocol/tips/blob/master/tip-1193.md), Tron wallets will provide a Provider interface by injecting a object to `window` to interact with the Tron blockchain.

The following table shows the object injected by wallets:

| Wallet | window.tron | window.tronLink | other variable |
|------|------|------|-----|
| TronLink | yes | yes | window.tronweb
| TokenPocket | yes | yes | window.tokenpocket.tron
| Bitget | yes | yes | window.bitkeep.tron 
| GateWallet |  yes | yes | window.gatewallet.tron 
| Okx |  no | yes | window.okxwallet.tronLink
| Bybit |  no | yes | window.bybitWallet.tronLink
| foxwallet(App only) |  no | yes | window.foxwallet.tronLink
| imToken(App only) |  no | no |  window.tronweb

### Injected order
We have tested the injected order of wallets and record the result as following. But it's not guaranteed that the order will be the same in all cases.

- `window.tron`: Bitget > TronLink > TokenPocket > GateWallet

  When users install multiple wallets and try to connect to TronLink, the TokenPocket extension or GateWallet extension will show the connection dialog.
- `window.tronLink`: Bybit > OkxWallet > TronLink
