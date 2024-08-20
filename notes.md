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




