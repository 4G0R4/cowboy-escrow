![AGORA](https://m.stacker.news/86894)

# Cowboy escrow
Cowboy Escrow is a censorship resistant peer to peer escrow built with bitcoin and nostr. It allows two parties to create an escrow contract, with an impartial third party "cowboy" acting as the escrow.

## Inspiration

[Smart Contracts Unchained](https://zmnscpxj.github.io/bitcoin/unchained.html)

## Before you start
You'll need to gather this information:
- [ ] 1. Maker (your) nostr npub _(you can create one new from here https://nstart.me)_
- [ ] 2. Maker (your) bitcoin onchain address to receive founds back in case something goes wrong
- [ ] 3. Taker's nostr npub
- [ ] 4. Taker's bitcoin onchain address
- [ ] 3. [@AGORA](https://iris.to/agora_sn)'s nostr npub `npub13kkpytvjcxsqka9pdshw3094urgh8fxwx7ru258lved9wr7f35mspal584`
- [ ] 4. [@AGORA](https://coinos.io/pay/AGORA)'s bitcoin onchain public address `bc1qrn8p4sn7hhng95pmvdkpnm4eqx0jv6ql2t98wf`


## How it works

1. The _Maker_ (can be either the buyer or the seller) creates a new contract by entering their details, the _Taker_'s details, _Escrow_'s details, contract terms and stake amounts. They then publish this to the Nostr protocol.

2. The _Taker_ views the contract details and can choose to accept or reject the contract. If they accept, they enter their nsec and sign the contract with their Bitcoin private key. They then publish this acceptance to Nostr, referencing the original contract event.

3. If there is a dispute, the _Escrow_ can view the contract details and decide on the outcome, declaring either the _Maker_ or _Taker_ as the winner by publishing the verdict to Nostr.

4. The contract funds are then released to the winner's Bitcoin address.

## Project stack

- `Nostr` for encrypted event publishing
- Noble `Secp256k1` for encryption/decryption and signing
- `Bech32` for npub/nsec encoding
- `BitcoinJS/TaprootJS` for Bitcoin script construction and signing
- `TailwindCSS` for styling

## Setup

1. Clone the repo

2. Open `index.html` in your browser to access the app

3. add `?network=testnet` to switch to Testnet3 network

4. There is no step 4

## Demo pic

![pic](https://github.com/ArcadeLabsInc/celebrity-escrow/assets/14167547/595d78d9-6a3d-4b67-a63a-118e86d0076e)
