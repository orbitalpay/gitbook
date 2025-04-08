---
description: Bridging together the cryptoverse's liquidity
icon: bridge-water
---

# Bridging In and Out

Your Orbital wallet is not isolated from other chains you are already familiar with. We use Aptos for the blazing fast transaction speeds they offer, making payments work within miliseconds. Apart from that, Orbital Pay is connected to the rest of the blockchains through Bridges.

Bridges connect to EVM chains (and soon Solana) to transfer funds in and our of Orbital Pay seamlessly. Bring USDC you already own in those networks to Orbital, and when you want, you can move them out as easily.

## Bringing money in

1. Go to [bridges.orbitalpay.xyz](https://bridges.orbitalpay.xyz/).
2. Ensure the destination is set to Orbital Pay. If not, click the swap button between the source and destination chains.
3. Connect your EVM wallet and choose the source chain you want to bring funds from.
4. Enter the destination wallet you want to receive the funds in. If you're coming to Bridges from [app.orbitalpay.xyz](https://app.orbitalpay.xyz), this information will be pre-filled to your Orbital account details.
5. Enter the USDC amount you want and click Proceed.
6. Confirm the Approve transaction.
   1. This transaction approves us to spend USDC, and does not move funds out of your wallet.
7. When the above transaction gets confirmed, you need to confirm the Burn transaction.
   1. This transaction burns the USDC on your source chain, ready to be minted to your Orbital wallet.

After doing the above, you wait till the funds appear in your Orbital wallet. EVM chains (like Ethereum, Base, Arbitrum, etc.) takes around 15 minutes to finalize, which is about as long as it'll take for the USDC to show up in your Orbital wallet.

## Taking money out

1. Go to [bridges.orbitalpay.xyz](https://bridges.orbitalpay.xyz/).
2. Ensure the source is set to Orbital Pay. If not, click the swap button between the source and destination chains.
3. Connect your Orbital account and choose the destination chain you want to shift funds to.
4. Enter the destination wallet you want to receive the funds in.
5. Enter the USDC amount you want and click Proceed. The transaction is prepared and sent for confirmation.

If the transaction succeeds and USDC has been deducted from your wallet, you just wait for them to show up in your destination wallet. Aptos finalizes very fast, so your funds would show up in your destination within a few minutes.
