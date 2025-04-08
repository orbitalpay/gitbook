---
description: Your account, no one else's.
icon: unlock
---

# Your wallet and safety

Orbital Pay wallets are self-custodial. This means only you have sole custody of your funds. We neither have the keys nor ability to access your wallet. We use Aptos Keyless to derive your wallet based on your Google Account authorization.

Get a more technical overview, look at Aptos's documentation below.

{% embed url="https://aptos.dev/en/build/guides/aptos-keyless/how-keyless-works" %}

## Can someone else access my funds?

The wallet you created is scoped to your Google account as well as Orbital Pay. This means the account can be accessed only is the Google account and Orbital Pay are used together. If any other app also has a social login feature, they won't have access to your account.

{% hint style="info" %}
We recommend you turn on multi-factor authentication in the Google account you use to log in to Orbital Pay.
{% endhint %}

## Can someone steal my keys?

Keyless works in a different way. There aren't traditional private keys that can be used to derive the wallet. Rather, the short-lasting JWT given by Google is paired with a temporary private key (which is created in your browser session) to create a signer that has access to the wallet. This means any temporary private key created during a session is valid as long as Orbital Pay is open, or 1 hour, whichever shorter.

We store the signer and temporary private key in a transient storage in your browser. Note that even during a session, if a hacker manages to steal the temporary private key, they can't access your account.

