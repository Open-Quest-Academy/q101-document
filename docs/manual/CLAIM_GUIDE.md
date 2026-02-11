<h5 style="text-align: center; font-size: 2em; font-weight: bold;">Airdrop Claim Guide - User Registration & Activation</h5>

## Airdrop Release Schedule Overview

The Q101 Airdrop uses a phased release mechanism consisting of three main stages:

## 📋 Stage 1: Registration & Activation

### What is this?

When claiming your airdrop for the first time, you must complete on-chain registration and activate your allocation. This process uses a **Commit-Reveal** two-phase security mechanism (a cryptographic method that prevents malicious actors from front-running your transaction).

### Important Notes

- ⚠️ **Permanent Wallet Binding**: The wallet address you use during registration will be permanently linked to your allocation. All future token claims must be made from this same address. **This cannot be changed.**
- ✅ **Zero Gas Fees**: All transaction fees throughout the process are covered by Q101 (powered by Gelato Relay).


## 🔒 Stage 2: Token Lock Period (Cliff Period)

*Note: This stage may or may not apply depending on your specific airdrop configuration. Check the Timeline Overview on the page for details.*

![time overview](docs/images/timeline-overview.png)

### What is this?

After activation, your tokens enter a waiting period during which they remain locked in the smart contract. No tokens are released during this stage unless an initial unlock amount is configured for your allocation.

### Key Information

| Item | Details |
|------|---------|
| Lock Duration | Check Timeline Overview (e.g., 180 days / ~6 months) |
| End Time | Displayed in UTC (e.g., 2026-08-10) |
| Initial Unlock Amount | One-time token release when the cliff period ends (shown in Timeline Overview card) |

### Tips

- The page displays a countdown showing remaining days, hours, and minutes.
- The system automatically advances to the next stage when the countdown reaches zero.


## 📈 Stage 3: Gradual Release

*Note: This stage may or may not apply depending on your specific airdrop configuration. Check the Timeline Overview on the page for details.*

### What is this?

During this stage, any remaining tokens are unlocked gradually over time through a linear vesting schedule.

### Important Rules

- ⏳ **Claim Cooldown Period**: You must wait a specified period between each claim. Refer to the "Next Claim IN" countdown displayed on the page for exact timing.
- ✅ **Tokens Never Expire**: Unclaimed tokens continue to accumulate and can be claimed at any time—you will never lose them.


## Prerequisites: Install a Web3 Wallet

Before starting the airdrop claim process, you must have a Web3 wallet installed. A Web3 wallet is a digital wallet that allows you to interact with blockchain applications and store your cryptocurrency assets.

The platform currently supports three wallet connection options:

- **MetaMask** - Browser extension wallet (most common for desktop users)
- **Coinbase Wallet** - Coinbase's self-custody wallet
- **WalletConnect** - Protocol that connects mobile wallets via QR code scanning


> **Note - Security Warning**:
>
> - Only download wallets from official websites to avoid malicious fake extensions.
> - Your private key and seed phrase (recovery phrase) are the **only** ways to access your wallet. If lost or compromised:
>     - ❌ You will **not** be able to claim remaining airdrop allocations
>     - ❌ You will **not** be able to recover tokens already claimed to that wallet
>     - ❌ There is **no** recovery option — not even the project team can help

## How to Register & Activate

### Step 1: Connect Your Wallet

- Go to the official airdrop claim page. Click the **"Connect Wallet"** button on the page.

![home](docs/images/home.png)


- **Accept the Platform's Agreements**

After clicking the "Connect Wallet" button, you will be prompted to accept the platform's agreements. Check **both** required checkboxes to confirm your acceptance, and click **"I Agree"** to proceed to the next step.
![platform agreements](docs/images/platform-agreements.png)

- **Connect Your Wallet**
![connect wallet](docs/images/connect-wallet.png)

#### Connect via MetaMask

In the wallet selection window, click **MetaMask**. Your browser will display a MetaMask popup window requesting connection. Click **Connect** to authorize the connection.

![metamask connect](docs/images/metamask-connect.png)

> **Note**: When registering for an airdrop or claiming tokens, MetaMask will display a signature request popup for your authorization.

![metamask connect](docs/images/metamask-signature-request.png)

#### Connect via Coinbase

In the wallet selection window, click **Coinbase Wallet**. Your browser will display a Coinbase Wallet popup window requesting connection. Click **Connect** to authorize the connection.

![coinbase connect](docs/images/coinbase-connect.png)
> **Note**: When registering for an airdrop or claiming tokens, Coinbase Wallet will display a signature request popup for your authorization.

![coinbase connect](docs/images/coinbase-signature-request.png)

#### Connect via WalletConnect

WalletConnect is a protocol that connects your mobile wallet to the website by scanning a QR code. It supports hundreds of different wallet applications.

Before proceeding, verify your mobile wallet supports WalletConnect:

<https://walletguide.walletconnect.network/>

![wallet connect QR](docs/images/wallet-connect-qr.png)

Using the **TokenPocket** mobile wallet app as an example, open the TokenPocket app on your mobile device. Scan the WalletConnect QR code displayed on your computer screen. Tap **Connect** to authorize the connection.

![TokenPocket connect](docs/images/token-pocket-connect.png)
> **Note**: When registering for an airdrop or claiming tokens, the TokenPocket app on your mobile device will display a signature request popup for your authorization.

![TokenPocket signature](docs/images/token-pocket-signature-request.png)

Once successfully connected, the page will display:

- **Your Balance** - The token amount available in your wallet
- **Connected Network** - The blockchain network your wallet is connected to
- **Account Address** - Your wallet's public address

![wallet connected state](docs/images/wallet-connected-state.png)


### Step 2: Registration & Activation

Using MetaMask Wallet as an example, once your wallet is successfully connected, you can begin the airdrop registration and activation process. Click the **"INITIATE CLAIM PROCESS"** button to proceed to the claim page.

![home registration activation](docs/images/home-registration-activation.png)

#### Step 2.1: Verify Voucher Code

After entering the airdrop claim page, you will need to provide your Voucher Code to verify your eligibility.

1. Ensure you are connected to the **BSC (BNB Smart Chain) network**
2. Enter your **Voucher Code** in the designated input field
3. Click **"Verify Voucher"** to submit and proceed to the next step

![verify voucher code](docs/images/verify-voucher-code.png)

**_Tips:_** _If you see a_ **_"Wrong Network"_** _displayed on the page, click the "Wrong Network" button to initiate a network switch._
![wrong network](docs/images/wrong-network.png)

#### Step 2.2: Registration

Before completing registration, review your allocation details and read the **Important Notes**. Check the checkbox to acknowledge you have read the notes, and then click **"Sign Registration"** to submit.

![registration](docs/images/registration.png)

A MetaMask popup will appear requesting transaction confirmation. Review the transaction information and click **"Confirm"** to approve and submit the transaction.

![registration transaction confirm](docs/images/registration-transaction-confirm.png)

#### Step 2.3: Activation

After completing registration, you need to activate your token allocation. Click the **"Activate Allocation"** button on the page.

![activation](docs/images/activation.png)

A MetaMask popup will appear requesting transaction confirmation. Review the transaction information and click **"Confirm"** to approve and submit the transaction.

![activation transaction confirm](docs/images/activation-transaction-confirm.png)

After successfully completing both Registration and Activation, one of two scenarios will occur:
- **With Token Lock Period/Gradual Release**: Your tokens will enter a **Token Lock Period** or Gradual Release schedule. A countdown timer will display the **next unlock time**.

![locked period](docs/images/locked-period.png)

- **Without Token Lock Period/Gradual Release**: The claiming process is complete, and your tokens are immediately available.

![allocation fully redeemed](docs/images/allocation-fully-redeemed.png)