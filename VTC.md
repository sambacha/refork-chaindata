# Vertcoin (VTC) was 51% attacked

## Preamble

Vertcoin is a Bitcoin clone that aims to be ASIC-resistant by hard forking to new mining algorithms whenever ASICs are deployed on the network. [Vertcoin was previously 51% attacked in Dec 2018](https://medium.com/coinmonks/vertcoin-vtc-is-currently-being-51-attacked-53ab633c08a4) and has since changed its proof-of-work algorithm to Lyra2REv3. On Nov 30th 2019, a Vertcoin miner noticed a large upswing in hashrate rental prices for Lyra2REv3 on Nicehash. This was combined with workers connected to Nicehash's stratum server being sent work for unknown (non-public) Vertcoin blocks. I contacted Bittrex, Vertcoin's most prominent exchange, to recommend they disable the Vertcoin wallet on their platform once it became clear an attack was in progress, which they subsequently did.

## The Attack

On [Sunday, 1 December 2019 15:19:47 GMT](http://hubris.media.mit.edu:5000/reorgs/65625) 603 blocks were removed from the VTC main chain and replaced by 553 attacker blocks. We note that 600 blocks is the current confirmation requirement for VTC on Bittrex. There were [5 double-spent outputs](http://hubris.media.mit.edu:5000/doublespends/VTC?reorg=65625) in which ~ 125 VTC (~$29) was redirected. Each of the double-spent outputs are coinbase outputs owned by the attacker and it is unknown to whom the coins were originally sent before being swept to an attacker address after the reorg.

- 18.33311434 VTC originally sent to vtc1qwnatpej2z5gm6qlhlvg90cpr8ly78hpf045lah and 6.66666666 VTC originally sent to vtc1qmvf89czpsee63xeghwk6469se8lng05ck7th4r in transaction 4ca37b55adf49d85f9c5a7f797f27703e1bd7246ae40d879b4af717abee09dd2
- 18.33311434 VTC originally sent to vtc1qeu5la72vcw4qf7ml3e7z7tnja6gdt7yl86z00u and 6.66666666 VTC originally sent to vtc1qwvj5ama3zqclm0h2dry9ltug392wup0ylsujp6 in transaction f4cb9e1b84f175ec6a41d316be0454837810d70d33669528ce2b87e1082c90d4
- 18.33337473 VTC originally sent to vtc1qz03flmgkjzd7jgwx3ul0c7fftclgfz5da63dtq and 6.66666666 VTC originally sent to vtc1q5306cezk7cls0lh29l2tfh07gnz0kkqf776aye in transaction a6e56ea963d1f29ed1cb44a17e24f77e6b6d0a8f945667c7fb88f11391c48ecb
- 23.999779 VTC originally sent to 3981xNMVBzfbXMoPCr3EojpbQXfpCdvLYV and 1 VTC originally sent to 3HeLfVTCjBRHtTp1s1Sra5peg58HMCR6kp in transaction 4522207fd077a05787cc74e8eb579922701dbf82e5da12c94f4dcece3d976b07
- 18.33311434 VTC originally sent to vtc1qw933nxhazxps5lfgqvc5mummcsya9688mek7f3 and 6.66666666 VTC originally sent to vtc1quhhqsexsf7x4pakf4a4jlypvzyqezgydh3wvk5 in transaction e7ae030fac290fe03fbfacaeb5f24a11114eeffdd8fb2b7e32543faea25eb708

Each of the above transactions were invalidated by a single transaction on the attacker's fork [77864705e247a9df8a427598b874afffc57469f5a79e06215b3d08e3d8c8df61](https://chainz.cryptoid.info/vtc/tx.dws?77864705e247a9df8a427598b874afffc57469f5a79e06215b3d08e3d8c8df61.htm) that sent 11000 VTC to [VqqBJ8BLW2q4dpiBTbCSC4PN3DHSKbFUCK](https://chainz.cryptoid.info/vtc/address.dws?VqqBJ8BLW2q4dpiBTbCSC4PN3DHSKbFUCK.htm) and 24.93491439 VTC to [3KFkRwvBbZtgBMpm8rPgc5Y545PiesMrdk](https://chainz.cryptoid.info/vtc/address.dws?3KFkRwvBbZtgBMpm8rPgc5Y545PiesMrdk.htm). This transaction swept the coinbase outputs from the attacker's blocks as well as double-spending the aforementioned outputs. The attacker mined with the address [VmoGb9SRaeTeVYGeoZxWAq71FHSCyPAPbm](https://chainz.cryptoid.info/vtc/address.dws?VmoGb9SRaeTeVYGeoZxWAq71FHSCyPAPbm.htm).

There is strong evidence this attack was performed using rented hashrate from Nicehash. The attack was originally discovered by inspecting the work being sent from Nicehash's stratum servers, which were sending work for non-public blocks. Below is a screenshot of a Nicehash miner's mining software console output showing work given for VTC block 1253804 when at the time the public block height of VTC was 1253800.

![](https://cdn.discordapp.com/attachments/370500771168518155/650388813625163856/unknown.png)

Post-attack analysis of the Nicehash orderbook during the attack's preparation shows a large upswing in hashrate rental price from the market equilibrium on both their EU and USA markets. Now that the attack is over, the rental price has returned to the baseline market equilibrium.

![](https://cdn.discordapp.com/attachments/365207777406091268/650793400651743252/Figure_1.png)
![](https://cdn.discordapp.com/attachments/365207777406091268/650793913363333143/Figure_2.png)

Based on the market prices during the attack's preparation and the difficulty of the blocks the attacker produced, we estimate the attacker spent between 0.5-1 BTC to perform the attack. The total value of the block rewards the attack received is 13825 VTC (~0.44 BTC). Given the attack was likely not profitable to perform based solely on block rewards, the motivation for the attack is not certain. Given the reorg was just deeper than 600 blocks (Bittrex's confirmation requirement for VTC), it is possible that Bittrex was the original target, but the double-spend portion attack was aborted due to Bittrex disabling their wallet before the fork could be released. It is also possible that no double-spend was ever intended, and the attack was a proof of concept or sabotage attack.
