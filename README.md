# DTemperature

### Diagram of Oracle Decentralized Temperacture
![1_Cs3w9iFmhIfkyg3Kg_FzFw](https://user-images.githubusercontent.com/72981260/160293147-f413a584-39de-4f9b-bcf2-9e50a5f0f234.png)

### Events of contract

Event that triggers oracle outside of the blockchain.
```
event NewRequest (uint256 id);
```
Event that triggers when there's a consensus on the final result.
```
event UpdatedRequest (
    uint256 id,
    uint256 agreedValue
  );
```

### Functions of contract

Called to emit event NewRequest.
```
function createRequest () external {
...
}
```

It is a getter of the oracle contract.
```
function getLastRoundData() external view returns (uint256) {
...
}
```


Called by the oracle to record its answer
It is a setter of the oracle contract.
```
function updateRequest (
    uint256 _roundId,
    uint256 _tempValue
  ) external {
...
}
```

### Address of Oracle contract on Rinkeby
You can see the latest temperature from the contract deployed the Rinkeby testnet.
https://rinkeby.etherscan.io/address/0x9038f129eD1273dfC233da0dB2D99c790d9E40F8#readContract

*Notes on DTemperature:*
+    The temperature should be converted uint value with 2 decimals
+    We can consider 27300 as 0'C
+    Example:
+       27200 => -10`C
+       27300 => 0`C
+       27400 => 10`C

