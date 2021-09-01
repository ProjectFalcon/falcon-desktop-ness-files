[![Platform:Windows](https://img.shields.io/badge/platform-Windows-lightgrey)](https://github.com/falcon/falcon-desktop/releases/latest)
[![Platform:macOS](https://img.shields.io/badge/platform-macOS-lightgrey)](https://github.com/falcon/falcon-desktop/releases/latest)
[![Platform:Linux](https://img.shields.io/badge/platform-Linux-lightgrey)](https://github.com/falcon/falcon-desktop/releases/latest)

# Falcon Desktop

![Falcon Desktop 3.0 Preview](.github-readme/falcon-desktop-3.0-preview.gif)

<p align="center">
   <a href="https://github.com/falcon/falcon-desktop/releases"><img src=".github-readme/button-download.png" alt="Download Wallet"></a>
   <a href="https://falcon.io"><img src=".github-readme/button-website.png" alt="Official website"></a>
   <a href="https://falcon.news"><img src=".github-readme/button-news.png" alt="Lastest news"></a>
   <a href="https://falcon.wiki"><img src=".github-readme/button-wiki.png" alt="Project wiki"></a>
</p>

**Table of Contents**

* [About](#about)
* [Participate](#participate)
* [Development](#development)
* [Troubleshooting](#troubleshooting)
* [Bug Bounties](#bug-bounties)
* [License](#license)

## About
The [Falcon Project](https://falcon.news/about/) is committed to providing everyone with privacy, security, resistance to censorship, and freedom in this digital age.

**Falcon Desktop** is a standalone, multi-purpose desktop application capable of hosting multiple functionalities at once and delivering a streamlined user-experience when interacting with Falcon's services and applications. 

Falcon Desktop provides easy access to the Falcon Blockchain and the SMSG protocol, hosts Falcon coin (PART) related wallets, gives users access to the Falcon Marketplace and the encrypted chat application. Additionally, Falcon Desktop supports a bot framework to optionally integrate interactions with third-party services within a user-friendly interface. Falcon Desktop generally refers to Falcon’s flagship application.

With **Falcon Desktop**, you get access to a decentralized platform delivering the following to you:

* **The Falcon Network** 
All services are peer to peer (p2p). No central authority or central server stands between you and the people you interact with. It's a direct connection.
   * **An encrypted data exchange protocol** 
SecureMessaging (SMSG protocol) is a decentralized storage network (DSN) to store and transfer data between nodes in a privacy-preserving manner. It enables a private and secure environment for e-commerce and communications between users. SMSG powers the Falcon Marketplace without bloating the blockchain with excessive data and without leaving any permanent record.
   * **A programmable blockchain with advanced privacy features** 
The Falcon Blockchain is a decentralized, immutable, and censorship-proof ledger. It is based on bitcoin technology and has been carefully enhanced by the Falcon team to provide a more robust level of privacy through industry-leading privacy technologies. The Falcon Blockchain processes and validates payments between two users without requiring any third-party such as a bank or a payment processor.
* **The privacy coin PART** 
PART is a blazing fast and highly flexible cryptocurrency with multiple privacy states. It lets you send and receive payments without revealing your financial data to anyone. The PART coin provides automation, interoperability, complete resistance to censorship, and privacy to the Falcon Marketplace.
* **The [Falcon Marketplace](https://falcon.io/marketplace)** 
The Falcon Marketplace is a decentralized and privacy-oriented marketplace that lets you buy and sell goods and services on the web without leaving any digital footprint behind. Payments between two users can be initiated using multiple currencies but always settle in PART. No bank account, documentation, email, phone number, or any other identification type is required. It transforms today's e-commerce into a free, secure, and trustworthy place where the market conditions are fair and equal to all.

Repositories: [Falcon Core](https://github.com/falcon/falcon-core) | [Falcon Marketplace](https://github.com/falcon/falcon-market) 

## Participate

### Chats

* **For developers** The developers chat [#falcon-dev:matrix.org](https://app.element.io/#/room/#falcon-dev:matrix.org) using [Element](https://element.io) (formerly Riot).
* **For community** Join the multilingual, open community chat [https://discord.me/falcon](https://discord.me/falcon) [![Discord](https://img.shields.io/discord/391967609660112925)](https://discord.me/falcon) with [Discord](https://discord.com).

[![Twitter Follow](https://img.shields.io/twitter/follow/FalconProject?label=follow%20us&style=social)](http://twitter.com/falconproject)
[![Subreddit subscribers](https://img.shields.io/reddit/subreddit-subscribers/falcon?style=social)](http://reddit.com/r/falcon)

### Installation

For non-developers curious to explore a new world of commerce, binaries can be downloaded and installed. It is the easiest way to get started.

[Download](https://github.com/falcon/falcon-desktop/releases/latest) 

There currently is an open testnet phase for the upcoming "Falcon V3" release. Feel free to test the new version; we happily look forward to your feedback.

[V3 Testnet Download](https://github.com/falcon/falcon-desktop/releases/)

## Development

[![Snyk](https://snyk.io/test/github/falcon/falcon-desktop/badge.svg)](https://snyk.io/test/github/falcon/falcon-desktop)
[![Build Status](https://travis-ci.org/falcon/falcon-desktop.svg?branch=master)](https://travis-ci.org/falcon/falcon-desktop)
[![Coverage Status](https://coveralls.io/repos/github/falcon/falcon-desktop/badge.svg?branch=master)](https://coveralls.io/github/falcon/falcon-desktop?branch=master)
[![Code Climate](https://codeclimate.com/github/falcon/falcon-desktop/badges/gpa.svg)](https://codeclimate.com/github/falcon/falcon-desktop)
[![Greenkeeper badge](https://badges.greenkeeper.io/falcon/falcon-desktop.svg)](https://greenkeeper.io/)

### Requirements

[Node.js®](https://nodejs.org/) v12, [git](https://git-scm.com/), and [yarn](https://yarnpkg.com/en/)

### Development install

NB!! Requires access to the private fork of this repo in order to obtain the latest build changes.

Clone the repo & fetch the dependencies:

```bash
git clone https://github.com/falcon/falcon-desktop
cd falcon-desktop
yarn install
```

> Note: The most recent development happens on the `dev` branch. Keep in mind that the development currently happens on a private fork of this repo. This repository is the user interface that works in combination with our [`falcon-core`](https://github.com/falcon/falcon-core).

In the project's folder:

1. Run `ng serve` to start the dev server and keep it running
1. In another terminal window, run `yarn run start:electron:dev -testnet --devtools` to start Falcon Desktop on testnet (the daemon will be updated and launched automatically)
   * `-testnet` – for running on testnet (omit for running the client on mainnet)
   * `-reindex` – reindexes the blockchain (in case you're stuck)
   * `--devtools` – automatically opens Developer Tools on client launch

#### Interact with falcon-core daemon

You can directly interact with the daemon ran by the Electron version:

```
./falcon-cli -testnet getblockchaininfo
```

### Packaging

#### Windows-only requirements

Building for Windows requires the 32-bit libraries to be available:

```
sudo apt-get install gcc-multilib
sudo apt-get install g++-multilib
```

#### Packaging commands

* `yarn run package:win` – Windows
* `yarn run package:mac` – macOS
* `yarn run package:linux` – Linux


## Troubleshooting

### Development issues

#### Blockchain syncing stuck

Restart the app with `-reindex` flag:

```
yarn run start:electron:dev -testnet --devtools -reindex
```

#### Marketplace fails to load

Delete the marketplace testnet `database` folder and restart the app:

| OS      | path                                                       |
|---------|------------------------------------------------------------|
| Linux   | `~/.falcon-market/testnet/03/`                            |
| Windows | `%APPDATA%/Falcon Market/testnet/03/`                     |
| macOS   | `~/Library/Application Support/falcon-market/testnet/03/` |

### Other issues

See our [Falcon Wiki](https://falcon.wiki/) for the most common problems or join [#falconhelp:matrix.org](https://app.element.io/#/room/#falconhelp:matrix.org) on [Element](https://element.io) for community help.

## Bug bounties

Falcon is a security and privacy oriented project. As such, a permanent bug bounty program is put in place in order to encourage the responsible disclosure of any bug or vulnerability contained within the Falcon code and reward those who find them.

[Falcon Bug Bounty Program](https://falcon.io/bug-bounties/)

## License

Falcon Desktop is released under [GNU General Public License v2.0](LICENSE).
