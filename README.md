# bitmessage [![Build Status](https://travis-ci.org/bitchan/bitmessage.svg?branch=master)](https://travis-ci.org/bitchan/bitmessage)

[![NPM](https://nodei.co/npm/bitmessage.png)](https://www.npmjs.com/package/bitmessage)

JavaScript Bitmessage library for both browserify and node. The goal of this project is to implement Bitmessage protocol v3 for both platforms at the maximum possible level (we still can't create TCP connections or listen for incoming connections in the Browser but the Proof of work and crypto is fully doable).

Public library API is currently in alpha stage, breaking changes are very likely to happen.

API documentation is available [here](https://bitchan.github.io/bitmessage/docs/).

## References

* [Bitmessage wiki](https://bitmessage.org/wiki/Main_Page)
* [Protocol specification](https://bitmessage.org/wiki/Protocol_specification)
* [Whitepaper](https://bitmessage.org/bitmessage.pdf)

## Feature matrix

- [x] Crypto
  - [x] SHA-1
  - [x] SHA-256
  - [x] SHA-512
  - [x] RIPEMD-160
  - [x] PRNG
  - [x] ECC keys manipulation
  - [x] ECDSA
  - [x] ECDH
  - [x] ECIES
  - [x] AES-256-CBC
  - [x] HMAC-SHA-256
- [x] Common structures
  - [x] message
  - [x] object
  - [x] var_int
  - [x] var_str
  - [x] var_int_list
  - [x] net_addr
  - [x] inv_vect
  - [x] encrypted
  - [x] service features
  - [x] pubkey features
- [x] Message types
  - [x] version
  - [x] verack
  - [x] addr
  - [x] inv
  - [x] getdata
  - [x] error
- [x] Object types
  - [x] getpubkey
  - [x] pubkey
  - [x] msg
  - [x] broadcast
- [x] WIF
- [x] POW
- [x] High-level classes
  - [x] Address
  - [x] UserAgent
- [ ] Network transports
  - [ ] TCP (Node.js only)
  - [ ] WebSocket
  - [ ] WebRTC
- [ ] Parse PyBitmessage configs
  - [ ] keys.dat
  - [ ] knownnodes.dat
  - [ ] messages.dat

## Usage

### Address

```js
var Address = require("bitmessage").Address;

// Generate a new random Bitmessage identity.
var addr1 = Address.fromRandom();
console.log("New random Bitmessage address:", addr1.encode());

// Or create it from passphrase.
var addr2 = Address.fromPassphrase("test");
console.log("Deterministic Bitmessage address:", addr2.encode());
```

## License

bitmessage - JavaScript Bitmessage library

Written in 2014 by Kagami Hiiragi <kagami@genshiken.org>

To the extent possible under law, the author(s) have dedicated all copyright and related and neighboring rights to this software to the public domain worldwide. This software is distributed without any warranty.

You should have received a copy of the CC0 Public Domain Dedication along with this software. If not, see <http://creativecommons.org/publicdomain/zero/1.0/>.
