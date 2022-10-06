![mev-boost](https://user-images.githubusercontent.com/116939/179831878-dc6a0f76-94f4-46cc-bafd-18a3a4b58ea4.png)

#


## What is MEV-Boost Uncensored?

MEV-Boost Uncensored is a fork of MEV-Boost which adds two new features.


* `censoring-relays` and `censorship-penalty` flags:
      * These flags allow you penalize the bids of relays that censor (or run toxic MEV like sandwiching) while still checking them for large payouts.  Bids from these relays will only be accepted if they bid at least `censorship-penalty` higher then relays included in the normal `relays` flag.  Both flags are denominated in Eth.

* `min-bid` flag
      * This flag allows you to build your own blocks locally if no relays submit a bid above your `min-bid` amount


Now you can keep a straight face when you say you are "here for tech", while sleeping soundly knowing you won't miss out on those really juicy MEV proposals.  So download MEV-Boost uncensored and put a price on your principals today.

## Mainnet example

This example setup will check the bloxroute ethical, bloxroute max-profit, and flashbot relays for bids.  It will only use the flashbots or max profit bids if they are at least 0.1 eth higher than the ethical relay's bid.

./mev-boost -mainnet -relay-check -relays https://0xad0a8bb54565c2211cee576363f3a347089d2f07cf72679d16911d740262694cadb62d7fd7483f27afd714ca0f1b9118@bloxroute.ethical.blxrbdn.com  --censorship-penalty 0.1 -censoring-relays https://0xac6e77dfe25ecd6110b8e780608cce0dab71fdd5ebea22a16c0205200f2f8e2e3ad3b71d3499c54ad14d6c21b41a37ae@boost-relay.flashbots.net,https://0x8b5d2e73e2a3a55c6c87b8b6eb92e0149a125c852751db1422fa951e42a09b82c142c3ea98d0d9930b056a3bc9896b8f@bloxroute.max-profit.blxrbdn.com

## More information

See the main [[MEV-Boost](https://github.com/flashbots/mev-boost)] repository for more detailed information.  This fork is identical to the original MEV-Boost software aside from the bid scoring algorithim.
