# Expanse (EXP) was 51% attacked

## Preamble

Expanse is a go-ethereum clone that uses Ethash (DaggerHashimoto), the proof-of-work mining algorithm used by upstream Ethereum. It is thus highly succeptible to rental mining attacks with over 70x Expanse's network hashrate available for purchase on Nicehash.

## The Attack

On [Monday, 29 Jul 2019 08:05:12 GMT](http://hubris.media.mit.edu:5000/reorgs/10845), 63 blocks were removed from the EXP main chain and replaced by 64 attacker blocks. There was [one double-spent account/nonce pair](http://hubris.media.mit.edu:5000/doublespends/1557) in which 200 EXP (~$12) was redirected.

- 200 EXP originally sent to account `0xa9ac4dc20cfc42e7c833d328971587e76b718135` from [`0x7129367f0abada8d9690ed1f896c490600fc6a8e`](https://explorer.expanse.tech/addr/0x7129367f0abada8d9690ed1f896c490600fc6a8e) in transaction [`0xdee58b67f7d87df1cd3c3cdcacec1c3e39d0d0248c97d23d7b2a32605386f983`](https://explorer.expanse.tech/tx/0xdee58b67f7d87df1cd3c3cdcacec1c3e39d0d0248c97d23d7b2a32605386f983)
- Coins redirected in the fork to `0x2f229972f47186a381eb819ec5083f3e51f20042` in transaction [`0x6230d958fb4524193670d89e4850998e08588fa09cd90a0f394c0733b16baaf2`](https://explorer.expanse.tech/tx/0x6230d958fb4524193670d89e4850998e08588fa09cd90a0f394c0733b16baaf2)

The attacker used various payout accounts for the blocks they mined, but used a single user agent in the extra data field of their blocks: `010817/geth/go1.11.2/linux`.

We note the original destination account of the coins [`0xa9ac4dc20cfc42e7c833d328971587e76b718135`](https://explorer.expanse.tech/addr/0xa9ac4dc20cfc42e7c833d328971587e76b718135) has been used prior to this attack with coins subsequently passing via account [`0xc41ef552ce503a75bbb3b3c82917df55edcfe54d`](https://explorer.expanse.tech/addr/0xc41ef552ce503a75bbb3b3c82917df55edcfe54d) and then to account [`0xc9710872d3e65edbf7f8776829dd7b21f2085e40`](https://explorer.expanse.tech/addr/0xc9710872d3e65edbf7f8776829dd7b21f2085e40) that holds ~9.3mil EXP which is around 90% of the total EXP supply. This strongly suggests the victim account was an exchange with significant cold storage of coins. At present Bittrex and Upbit represent ~70% and ~30% respectively of Expanse's trading volume.
