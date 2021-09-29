# January 23 - February 5 reorgs (no defense)

We call the addresses of the miners who receive the mining rewards in a reorg the “attacker” and the addresses double spent are the “victim.” The receipt timestamps are when our reorg tracker observed the blocks of a new chain become the most-work chain. “Depth” is the number of blocks that were removed from the most-work chain as a result of the reorg and “length” is the number of blocks that replaced the existing blocks in order to cause a reorg. The attacker had an expected 2.53 MH/s of hashrate to conduct one of the attacks. The overall BTG hashrate was between 2-2.5 MH/s in the days before the attack.

| Time                | Attacker         | Depth | Length | Amount (BTG) | Expected Hashrate\* (MH/s) | Expected Nicehash\* Cost (BTC) |
| ------------------- | ---------------- | ----- | ------ | ------------ | -------------------------- | ------------------------------ |
| 2020-01-23 18:01:32 | GWrW5dT          | 14    | 13     | 1900         | 2.53                       | 0.2013653                      |
| 2020-01-23 20:06:16 | GWrW5dT          | 4     | 5      | 3737         | 1.44                       | 0.06209329                     |
| 2020-01-24 00:24:08 | GWrW5dT          | 15    | 16     | 3320         | 1.57                       | 0.21731648                     |
| 2020-01-31 09:49:40 | GUmkmEX, GXaCThK | 3     | 3      | 0            | 0.67                       | 0.04300389                     |
| 2020-01-31 16:32:47 | GUmkmEX, GXaCThK | 8     | 9      | 0            | 1.64                       | 0.10404223                     |
| 2020-02-01 08:45:22 | GUmkmEX, GXaCThK | 4     | 4      | 0            | 1.26                       | 0.05009885                     |
| 2020-02-01 09:33:27 | GUmkmEX, GXaCThK | 4     | 5      | 0            | 2.36                       | 0.06787932                     |
| 2020-02-05 06:16:46 | GKGUq2p, Gh46Jw1 | 9     | 10     | 1980         | 1.45                       | 0.11605818                     |

\* _Expected hashrate is calculated based on the total chainwork accumulated on the fork divided by the time taken to generate the fork based on the block timestamp. The expected Nicehash cost is calculated by multiplying the ZHash rental market spot price at the time of the fork block by the expected hashrate and the estimated time to generate the fork (this reduces to the total chainwork multiplied by the rental price)._

# Feb 8th repeated counterattack

| Height | Timestamp | Attacker/Original | Double-spend | Hash                                                             | Miner address(es)                                                        | Chainwork Delta |
| ------ | --------- | ----------------- | ------------ | ---------------------------------------------------------------- | ------------------------------------------------------------------------ | --------------- |
| 619934 | 04:04:34  | Fork              |              | 0000000239ee124dfb934c244fba10465e8d03aa655f96a47c6aefea5653e8b0 | GJjz2Du9BoJQ3CPcoyVTHUJZSj62i1693U                                       | 0.00            |
| 619935 | 04:20:12  | Attacker          | \*           | 00000001bd611ce076d502d64c5c10a2a5eca3011df502851c64eab4b026372d | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 30.68           |
| 619935 | 04:22:02  | Original          | \*           | 000000018039df312dcf5d7717f8a749dfd743f1624eba92e4152434b5fc59d3 | GK18bp4UzC6wqYKKNLkaJ3hzQazTc3TWBw                                       | 30.68           |
| 619936 | 04:55:12  | Attacker          |              | 00000001cf5c4981a536c14edc213d5ad70a3204f4ae0cddb65953a5ee17769b | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 31.65           |
| 619937 | 04:57:27  | Attacker          |              | 00000001ef4bbbc413a0bc35c1cd60b4e00e51e8c4a24f1e21461f480c590712 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 32.18           |
| 619936 | 05:20:42  | Original          |              | 0000000232512c8ce9206bc465bf21935f984c8ac044315db0fe526542882f00 | GeNNVzHUpD1p9S5Wz9E9vW86Ars82cokPu                                       | 31.65           |
| 619937 | 05:30:39  | Original          |              | 0000000146910a8f41d4c104b7db8121aa247278b12264af0f94e2097a81926f | GJjz2Du9BoJQ3CPcoyVTHUJZSj62i1693U                                       | 32.13           |
| 619938 | 05:39:05  | Attacker          |              | 0000000231174f7ea65a5a3db70dc819313d3dca5c9dce8f1552912aa3284bcc | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 32.58           |
| 619938 | 05:39:34  | Original          |              | 000000010cec0962bf427c7647de7af632a213941052b6a929ca69e521340c70 | GJjz2Du9BoJQ3CPcoyVTHUJZSj62i1693U                                       | 32.49           |
| 619939 | 06:07:04  | Original          |              | 00000002248e7b57c202065193861e41ad2191e7f6fd6dcc82546175a32f3fed | GezKoZ59mhmpMzjNBWNoYKvLhFLAdHuL6P<br>GP8Kd2o6xu9qqj1K1qFuM2Ls3FBZ2Sm5tV | 32.78           |
| 619939 | 06:21:06  | Attacker          |              | 00000000abd9cfea4a3d65054bbb410306ea0645c47cf022c564c2ea28c11f08 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 32.85           |
| 619940 | 06:23:21  | Original          |              | 00000002b7aa1a2ac8003e4dd68279173d63f62881a298b2c06fc6fd3f4c1259 | GezKoZ59mhmpMzjNBWNoYKvLhFLAdHuL6P<br>GP8Kd2o6xu9qqj1K1qFuM2Ls3FBZ2Sm5tV | 33.01           |
| 619941 | 06:34:34  | Original          |              | 000000014863587ddf6b30cd9ac1ad66a57c46db335e839d60d93bdea2566182 | GezKoZ59mhmpMzjNBWNoYKvLhFLAdHuL6P<br>GP8Kd2o6xu9qqj1K1qFuM2Ls3FBZ2Sm5tV | 33.20           |
| 619940 | 06:40:13  | Attacker          |              | 000000014d44e7f4be3c3a3a7ff93c113410c2d7fb0d2cc039000bf0fa787084 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 33.06           |
| 619941 | 06:42:23  | Attacker          |              | 00000000208215a321b7e52d0c20c7cddc722f573f5b17744152a8e14e63cdf5 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 33.24           |
| 619942 | 06:46:55  | Original          |              | 00000003116cd284a98aed1fd50cb476ccfac9bd8a1ee4a1190e11966d9c3614 | GJjz2Du9BoJQ3CPcoyVTHUJZSj62i1693U                                       | 33.37           |
| 619943 | 06:51:25  | Original          |              | 00000001662698e437de0af21053cc73d519415c0a4978a985fbd80b90417888 | GezKoZ59mhmpMzjNBWNoYKvLhFLAdHuL6P<br>GP8Kd2o6xu9qqj1K1qFuM2Ls3FBZ2Sm5tV | 33.52           |
| 619942 | 06:52:25  | Attacker          |              | 00000001289e7c1409d64fbf2595b3e5b2f67658c94785ac6afe3db8bf984de5 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 33.40           |
| 619943 | 06:53:19  | Attacker          |              | 0000000061f354083d79bca172e6073d9b09e817ecc3eb21db87ddf2af9a5c2c | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 33.54           |
| 619944 | 06:55:09  | Attacker          |              | 0000000339b0f8b6975a0c707f4a395716405f6d9576b1674c8e364acb6c5f08 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 33.68           |
| 619945 | 06:58:56  | Attacker          |              | 000000020704fc446b4ee74a9856678e2bff9d6d167bd34cf93c140825cc283a | GP4MnT7Xm4ahZhRcWFaqPGkZknMda1XuzA                                       | 33.80           |
| 619946 | 07:07:17  | Attacker          |              | 00000003353fc61940b7ad9211597b275dc39b7f51643296a27f91621d899409 | GezKoZ59mhmpMzjNBWNoYKvLhFLAdHuL6P<br>GP8Kd2o6xu9qqj1K1qFuM2Ls3FBZ2Sm5tV | 33.92           |
| 619944 | 07:20:16  | Original          |              | 00000003047990c0f3de16ce1a829a020f4c664ffe4191b18c9d3af19e2ea2d2 | GbWi6y7c6UT1Ee9GzteUPuqiKMT6kUgDua                                       | 33.66           |
| 619945 | 07:29:03  | Original          |              | 0000000137b998348adb6743d9fa1e03219b2ffaebbd36c09cef248c829d48c6 | GbWi6y7c6UT1Ee9GzteUPuqiKMT6kUgDua                                       | 33.78           |
| 619946 | 07:32:55  | Original          |              | 00000001d1caede1fd6399c328fc52e9e0ec516341f524df74595f8e3422e99f | GbWi6y7c6UT1Ee9GzteUPuqiKMT6kUgDua                                       | 33.89           |
| 619947 | 07:33:47  | Original          |              | 000000007816c271ec1e14b74d1d993fd75767376dfd729ab27d1abd3c00be73 | GbWi6y7c6UT1Ee9GzteUPuqiKMT6kUgDua                                       | 33.99           |
| 619948 | 07:37:23  | Original          |              | 00000000f638d18cc908bc5aa0e4f0c6df6b59bc238668b5de08a7d863121d1d | GK18bp4UzC6wqYKKNLkaJ3hzQazTc3TWBw                                       | 34.09           |
| 619949 | 07:38:48  | Original          |              | 0000000348977a28361416976445832db3123e225f4c7243da8fbf31c012b639 | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.19           |
| 619950 | 07:41:16  | Original          |              | 00000001f4c7a3e631a9f716f22bcfff032cadab1c886917fa71dd64007e8a43 | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.28           |
| 619951 | 07:51:26  | Original          |              | 00000000a2b6099d74e8c14f43ecf5c3c78bce247e112565ce7a600107d6f11e | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.37           |
| 619947 | 07:53:46  | Attacker          |              | 000000005b8f597b44143654aaca261bef61c707e2ea65a67f43c095f57af3d1 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.04           |
| 619952 | 08:04:13  | Original          |              | 0000000085e7d9b9017e5408cbfcf64427212e30eb2f071189ea8001a89b78e5 | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.45           |
| 619953 | 08:10:32  | Original          |              | 0000000299a6b651fab7a499c8d3f19419bd2392f6e9c9e3469bfe915c5d07c2 | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.53           |
| 619948 | 08:12:01  | Attacker          |              | 00000001a173da8d0ac68351a899f2595c23951d4ab65fdb253e440ebe127693 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.13           |
| 619954 | 08:12:33  | Original          |              | 000000016fc42421b5046836792d934bc0b7c9051ed47845c583886c7cb7bddf | GJjz2Du9BoJQ3CPcoyVTHUJZSj62i1693U                                       | 34.61           |
| 619949 | 08:15:08  | Attacker          |              | 000000014825db1df9b6c47c0f15c96e67a58eaa5c73661e8bf82cb544353785 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.21           |
| 619955 | 08:22:50  | Original          |              | 00000000b9bdd518227b8c36c5b7871e07fdd257631a78c3be984b514dba15ba | GK18bp4UzC6wqYKKNLkaJ3hzQazTc3TWBw                                       | 34.68           |
| 619950 | 08:24:33  | Attacker          |              | 00000001955bc349fc1540a5834d86dad5e61e639db1cb509443f8bdf76d4ae0 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.29           |
| 619951 | 08:26:57  | Attacker          |              | 00000001dee68cee5c2062a545f4ec219368c43626f00f4baa180ed10fa1f12b | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.37           |
| 619952 | 08:33:44  | Attacker          |              | 000000016bbe4d4d86283daeaa8d7104ee0d697bbc8e435e0b63bb964d272ec6 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.44           |
| 619953 | 08:45:54  | Attacker          |              | 00000003a17a854629d53c3fee8520f6f9444ee619ec03d1e5bd4d3e7a567ab2 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.51           |
| 619954 | 08:47:30  | Attacker          |              | 0000000349ef71330105504f52d9ee6bf9fa79aec29f6446eb808d6fdf2f3e97 | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.58           |
| 619955 | 08:54:21  | Attacker          |              | 0000000029e2fd85c3f70188ad8e0bb2924b66e18a594908bea2807c95de652c | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.64           |
| 619956 | 08:58:01  | Attacker          |              | 00000002d50fd8140a07d2db4a2afbbd13a5ca14b7bf7e11c872e8c11b81eefb | Gh46Jw1vCtg3iqLQdMhHAWTaKTH3sB1Xex<br>GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD | 34.71           |
| 619957 | 09:09:43  | Attacker          |              | 00000002c5963b7b3cd9ea53879e51f9ba53691553f0877467a13c3e1ba881a7 | GSraCk7RFQsg6yJAQ4XU5bcRRBHVnwX88j                                       | 34.77           |
| 619956 | 09:14:35  | Original          |              | 000000023b7ea36e75782bb8d1cdf0bdc77e84afe8b7a0add800c1dd566970b1 | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.75           |
| 619957 | 09:27:43  | Original          |              | 000000026bf63cf2bb5dbc414a9ff62ebe6d4b17530271b28d1debaf4cd78041 | GSsjeTZzaatwZS7J978DQzv322eAr79KLp                                       | 34.81           |

# Transaction Data

In the following analysis we examine the actual transactions that were double-spent. For simplicity, we write only the prefixes of txn IDs and addresses (included in full below), and we disregard addresses in the transactions which received or sent less than 1 BTG (~10 USD as of Feb 2020). All units are in BTG.

This retaliation game started when the attacker reorg’d out transactions [757](https://btgexplorer.com/tx/757863a448198c40e27c718a47159a51c4ba3ac698c4a3598a94df36fbbaa4ae) and [d5f](https://btgexplorer.com/tx/d5ffe8de9e417de3b5db67ae3276bc490e253bae33f2eaef1b934b933c14384b) and replaced them with transactions [50d](https://btgexplorer.com/tx/50d2d947a0ff8ff199daa25bbb8a8b28ae6e0ef099d4713d161e462caa4b5608) and [f38](https://btgexplorer.com/tx/f387bf7793a4a04f9f3df12b2d5de24a24decd78de207e802d0bda899c28001c). In both pairs, the second transaction spends outputs from the first, that is if the first transaction is invalidated due to a double-spend, the second transaction is also invalidated. We can therefore think of the pair of transactions as units. We will use the following format to describe the transactions, with TxID standing for transaction IDs, the plus indicating that we're considering the net inputs and outputs of the combination of the two transactions, InAddr1 as the first input address of the transaction and amt1 as the amount sent from that address.

```
TxID1 + TXID2:  InAddr1 amt1, InAddr2 amt2, InAddr3 amt3 -> OutAddr1 amt4 OutAddr2 amt5

757 + d5f:  GTZ 2124, GKE 2140, GKG 125 -> AYP 2439, AbC 1951

50d + f38:  GTZ 2124, GKE 2140, GKG 125 -> GVe 3271, GYz 1119
```

Note the inputs to the pairs of transactions are the same. The key difference is in the outputs, which gives us an indication of what was 'stolen' from what addresses.

From this we can conclude that, in total, 4390 BTG (roughly 44,000 USD) was 'stolen' from AbC and AYP and sent instead to GVe and GYz.

Full transaction IDs and addresses below:

- 757863a448198c40e27c718a47159a51c4ba3ac698c4a3598a94df36fbbaa4ae
- d5ffe8de9e417de3b5db67ae3276bc490e253bae33f2eaef1b934b933c14384b
- 50d2d947a0ff8ff199daa25bbb8a8b28ae6e0ef099d4713d161e462caa4b5608
- f387bf7793a4a04f9f3df12b2d5de24a24decd78de207e802d0bda899c28001c

Full addresses below:

- GKGUq2p4WSFT4zAJNLa8QggnZiPdBc1TTD
- GQgZ6ywGs2E1f1feGzPmooZmA6J19Jfktu
- AbCNuEYdL6f4VumChQYT9W5MMSVs7pafdD
- GYzEgquu6RNuiaZ7U8b51LQvKJQkepWhmh
- GTZ3DotMqbdzNEMrZgDmuNBb6UezLLQHKc
- GKEhWaCTzkYWgwnQnfB2kHzAjrWf5Q4ZNS
- AYP46aBYEEuBjgVeSg1xaCxM97wKeXsfvc
- GVeNG66p5BrQEm1LYnZzhQ4m7c6tNk16vp
