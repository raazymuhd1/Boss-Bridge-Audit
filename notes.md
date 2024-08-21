## Checklist for all attack vector
 - [cyfrin-solodit](https://github.com/Cyfrin/audit-checklist/blob/main/checklist.json)


## Signing and Verifying signature

 [**Resources for EIP-712**](https://eips.ethereum.org/EIPS/eip-712) 
 
 - Signin message:
   - Take private key + message (calldata/function selector + parameters)
   - hash it using ECDSA algorithm, and the returns output will be `signed message / v, r, s` that later we can use to verify the signature. 

 - Verifying message:
   - Get the signed message, break into `v, r, s`
   - get the data itself, and use it as input parameters for `ecrecover`


## EVM Diff
 see the differences of each EVM chains, something like opcode differences and etc
 - resources [evm-diff](https://www.evmdiff.com/)


## MEV
  extracting value from the chain, it could be by frontrunning, sandwich attack to get more profit from someone else's transactions by looking into `mempool`. Cause each transaction is being stored in `mempool` before it gets included in the block by block proposer or after it gets validated by validator.

## Slippage protection
  `slippage protection` is good for users to protect them from losing money when doing swaps on any dex, because when they are doing swap lets say $2000 worth of ETH for USDT, And their transaction might not being executed right away (still in the mempool). node will executed other transactions that pays high fees to them, And if that other transactions was trying to buy the same pairs of token as we did but they did it for higher amount than us. then the price will be changes bfore our transaction is executed, therefore we will get less than what we expected we do our swap transactions. 

  But with slippage protection we can avoid losing too much money from doing swap, by set slippage tolerance up to how many percentage we are still willing to pay to get the exact amount after the price is changing bfore our transaction executed. if we are about to lose above the percentage that we set, then the transaction will revert and its protected us from losing more money.

