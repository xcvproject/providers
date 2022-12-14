# EVM Providers

lightweight evm providers

## Install

```bash
npm install -D @xcvproject/providers
```

or

```bash
yarn add -D @xcvproject/providers
```

## Usage

### Check is Ethereum available

```typescript
import { isEthereumAvailable } from '@xcvproject/providers';

if (isEthereumAvailable) {
  // ethereum is available
}
```

### Web3Provider

```typescript
import { Web3Provider } from '@xcvproject/providers';

// available options
-eth_requestAccounts - wallet_addEthereumChain;

// connect wallet
Web3Provider.send('eth_requestAccounts', [])
  .then(console.log)
  .catch(console.error);
```

#### SignMessage

```typescript
const signer = Web3Provider.getSigner();
const signature = await signer.signMessage('Message');
```

### Contract

```typescript
import { Contract } from '@xcvproject/providers';

// connect to contract
const address = '';
const abiOrInterface = [];
const dapp = new Contract(address, abiOrInterface);

dapp[method]();
```

### Fraction

```typescript
import { FractionToApy, ApyToFraction } from '@xcvproject/providers';

const fraction = ApyToFraction(12.2); // 12.2% APY

const apy = FractionToApy(fraction[0] / fraction[1]);
```

### Constants

```typescript
import { constants } from '@xcvproject/providers';

// available constants
constants.AddressDead;
constants.AddressZero;
constants.MaxInt256;
constants.MaxUint256;
constants.MinInt256;
constants.Zero;
```

### Utils

```typescript
import { utils } from '@xcvproject/providers';

// available utils
utils.formatBytes32String();
utils.parseBytes32String();
utils.checksumAddress();
```
