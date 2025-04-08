---
description: Currently we are inviting specific merchants to use Orbital Pay
icon: cart-arrow-down
---

# Onboarding as a merchant

We soon plan to open up this process for everyone. For now, this section is for people onboarded as a merchant. If you want prioritised access to Orbital Pay's Merchant Console, please [fill this form](https://docs.google.com/forms/d/e/1FAIpQLSeJKaRmqXK93pIv1ZDUMxd-OczuKJUULxybK6qkUyBV1J8UUw/viewform?usp=dialog).

<figure><img src="../.gitbook/assets/merchant page.jpeg" alt=""><figcaption><p>Merchant Console</p></figcaption></figure>

Merchants will see additional tabs on their screen for the console and transaction history.

## Merchant Console

This is the admin dashboard where you can create keys. The keys are intended for backend integration, but are needed to set you up as a merchant. Once you create them, you're good to go.

You can also configure a Callback URL here, where you will be updated regarding state changes to your payments (such as when a user pays, a session times out, or the user declines). This is usually used in conjunction with automated checkouts.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>Flow of funds from the user to you</p></figcaption></figure>

### Payment timeframes

* Natively through Orbital Pay: Couple of seconds (typically less than 2s)
* Aptos Wallets: Couple of seconds (typically 2s - 5s)
* Solana Wallets: Around a minute (typically 40s - 1m)
* Sui Wallets: Around a minute (typically 30s - 1m)
* EVM Chains: Around 15 minutes

For EVM Chains, we depend upon the source chain to finalize, which takes 12-13 minutes according to EVM's consensus mechanism and is outside our control. However almost all transactions which show `processing` will be finalized.



