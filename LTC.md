# Litecoin Cash (LCC) was 51% attacked

## Preamble

Litecoin Cash is a Bitcoin Core clone which uses a hybrid Proof-of-Work/Proof-of-Stake consensus algorithm in an attempt to aleviate 51% attacks on its network. LCC's PoW algorithm is SHA256 but its network hashrate is many orders of magnitude smaller than Bitcoin's, making it highly vulnerable to 51% attacks, as was [demonstrated last year](https://www.ccn.com/litecoin-cash-latest-small-cap-altcoin-to-suffer-51-percent-attack/). The [LCC whitepaper](https://hive.litecoinca.sh/whitepaper.pdf) describes a system they call "Hive Mining", which is effectively a PoS lottery in which users can purchase "bees" (lottery tickets) that have the potential to be eligible to propose a PoS block for each new PoW block. In the paper, the authors claim this scheme provides "protection" from 51% attacks by interlacing PoW and PoS blocks, and giving PoS blocks more relative weight than PoW blocks in the chain-work calculation for selecting the most-work block.

## The Attacks

The deep reorgs are summarised below. Each event gives the time the reorg occured from our LCC full node's perspective, the number of blocks removed from the main chain in the reorg, and the number of attacker blocks that replaced them. Also provided are the high-level details of any double-spends caused by the reorg. All times are in GMT.

- [Thursday, 4 July 2019 08:57:24 - 48 blocks removed, 41 blocks added](http://hubris.media.mit.edu:5000/reorgs/2219)
  - No double-spends detected
- [Friday, 5 July 2019 08:42:58 - 102 blocks removed, 64 blocks added](http://hubris.media.mit.edu:5000/reorgs/2560)
  - 28,000 LCC double-spent (~$317)
  - Coins originally sent to `MKKbmesxvDY1rYbJ8GojY7azorLZyNf5Cc`
  - Returned to `CaBtdSSrXBn8k4MjH58QNqGtNfaYAyKXqZ` in transaction [145a8e54e8e6c866a3976d9d3233dc3390147acab29d73e7fa757fdb06534056](https://chainz.cryptoid.info/lcc/tx.dws?145a8e54e8e6c866a3976d9d3233dc3390147acab29d73e7fa757fdb06534056.htm)
- [Friday, 5 July 2019 15:26:55 - 63 blocks removed, 50 blocks added](http://hubris.media.mit.edu:5000/reorgs/2639)
  - 66,000 LCC double-spent (~$747)
  - Coins originally sent to `MKKbmesxvDY1rYbJ8GojY7azorLZyNf5Cc`
  - Returned to `CaBtdSSrXBn8k4MjH58QNqGtNfaYAyKXqZ` in transaction [48459dd4aef12806176ab49bc79751751403645f1b7d205ec5bb5708c8c29fa9](https://chainz.cryptoid.info/lcc/tx.dws?48459dd4aef12806176ab49bc79751751403645f1b7d205ec5bb5708c8c29fa9.htm)
- [Saturday, 6 July 2019 01:55:06 - 73 blocks removed, 57 blocks added](http://hubris.media.mit.edu:5000/reorgs/2781)
  - 80,000 LCC double-spent (~$903)
  - Coins originally sent to `MKKbmesxvDY1rYbJ8GojY7azorLZyNf5Cc`
  - Returned to `CaBtdSSrXBn8k4MjH58QNqGtNfaYAyKXqZ` in transaction [b26d6b77ea25090a2e7b2d9037577340bdbe2570ab1446b6020edaf5010406c8](https://chainz.cryptoid.info/lcc/tx.dws?b26d6b77ea25090a2e7b2d9037577340bdbe2570ab1446b6020edaf5010406c8.htm)
- [Saturday, 6 July 2019 08:19:53 - 91 blocks removed, 68 blocks added](http://hubris.media.mit.edu:5000/reorgs/2894)
  - 160,000 LCC double-spent (~$1827)
  - Coins originally sent to `MKKbmesxvDY1rYbJ8GojY7azorLZyNf5Cc`
  - Returned to `CaBtdSSrXBn8k4MjH58QNqGtNfaYAyKXqZ` in transaction [46197e2068f8b7511add3e7791fdb06ce44bb5ab0be7320531ada6ef79097cfa](https://chainz.cryptoid.info/lcc/tx.dws?46197e2068f8b7511add3e7791fdb06ce44bb5ab0be7320531ada6ef79097cfa.htm)
- [Sunday, 7 July 2019 03:14:56 - 37 blocks removed, 19 blocks added](http://hubris.media.mit.edu:5000/reorgs/3152)
  - 150,000 LCC double-spent (~$1717)
  - Coins originally sent to `MKKbmesxvDY1rYbJ8GojY7azorLZyNf5Cc`
  - Returned to `CaBtdSSrXBn8k4MjH58QNqGtNfaYAyKXqZ` in transaction [23aedc186c22852e641fd498b68703aa6580198afff581e7e57551d0dfe2e4de](https://chainz.cryptoid.info/lcc/tx.dws?23aedc186c22852e641fd498b68703aa6580198afff581e7e57551d0dfe2e4de.htm)

In each case the attacker did not mine any PoS blocks, producing their higher-work chain purely through PoW blocks. The increase in difficulty this caused while producing their alternative chain is the reason for the attacker's chain being shorter in terms of blocks than the original chain it replaced, which was interlaced with PoS blocks. Each reorg appears to have been performed in sequence, with the set of attacker blocks from the prior reorg containing the transaction to be double-spent in the subsequent reorg. It is unclear who the victim address (`MKKbmesxvDY1rYbJ8GojY7azorLZyNf5Cc`) belongs to, but the pattern of attacker behaviour of repeated deposits and double-spends suggests it is an attempt to drain an exchange wallet of coins.

We observe that the [LCC code](https://github.com/litecoincash-project/litecoincash/blob/adcfb6f9437a89f212fa9341d453ae1d4809ace7/src/chain.cpp#L123) does not appear to include a higher relative weight for PoS blocks as described in the paper, which perhaps made the job of the attacker easier. However, there is no requirement for a certain number of PoS blocks to be generated per PoW block beyond the difficulty adjustment algorithm, and the attacker was able to simply rent more hashrate to compensate for the increased PoW difficulty, which would remain possible at any reasonable relative weighting.
