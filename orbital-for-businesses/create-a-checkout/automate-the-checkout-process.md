---
icon: computer-mouse-scrollwheel
---

# Automate the Checkout process

Automating checkouts require you to manage your backend. We have 2 lightweight SDKs you can plug in to your Backend and Frontend respectively.

## Creating Checkout Sessions

Any Create action happens through your backend and it requires your private key. Install [our backend SDK](https://www.npmjs.com/package/@orbitalpay/backend) using:

```sh
npm install @orbitalpay/backend
```

Using this you can create a checkout session (which will give you a transaction ID):

```typescript
const client = new OrbitalPayBackendClient(process.env.privateKey!, process.env.publicKey!);

const amount = 3.14;
const description = "Trying out the Backend SDK";

// Create a new checkout session
const checkout = await client.createCheckoutSession(amount, description);
```

Checkout is of the format:

```javascript
{
  success: true,
  data: {
    // Note that the amount is the value you entered times 10^6
    // This is a standard precision conversion we do to deal with USDC amounts
    // Divide the amount by 1e6 for the dollar value
    amount: 3140000,
    details: 'Trying out the sdk',
    token: 'USDC',

    // this is the transactionId you will use in the frontend SDK
    transactionId: 'mrc_2025-xxxx_xxxx_xxxx',

    timestamp: 1744107706053,
    requesterWallet: '0x<your wallet address>',
    status: 'pending',
    type: 'merchant',
    
    emailLinked: false,
    expirationTimestamp: null,
    txhash: null,
    callbackUrl: '<your callback url>'
  }
}
```

You would store this checkout object, or at least the transactionId in your backend against your user or user's purchase details. In your merchant console, you get an option to configure a Callback URL, where we post details once the user has paid or declined the transaction.

## Fetching Checkout Sessions

You can see the checkout sessions on your merchant console. You can also fetch them individually or the entire history using our backend SDK.

```typescript
// Query the checkout session to see the state, transaction hash (if paid) and other details
const checkoutSession = await client.fetchCheckoutSession(checkout.data?.transactionId);

// Fetch all historical checkout sessions created by your merchant
const historicalCheckouts = await client.fetchHistoricalCheckoutSessions();
```

The `fetchHistoricalCheckoutSessions` is paginated, it allows you to use multiple parameters:

```typescript
// Number of items to fetch
// defaults to 10
const count = 20;

// Timestamp of the last item fetched in the previous call
// default to undefined
const last_timestamp = 1690000000;

// Order of the items
// default: "ASCENDING"
// possible values: "ASCENDING" or "DESCENDING"
const order = "ASCENDING";

// Any of the parameters can be skipped/omitted
const historicalCheckouts = await client.fetchHistoricalCheckoutSessions({
  count,
  last_timestamp,
  order,
});
```

## Integrating Orbital Gateway on your Frontend

Our [frontend SDK](https://www.npmjs.com/package/@orbitalpay/sdk) allows you to integrate our payment interface with just a button. Install the SDK using:

```sh
npm install orbital-pay-sdk
# or
yarn add orbital-pay-sdk
```

Now in your frontend, you can directly use:

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Frontend SDK: Sample Integration</p></figcaption></figure>

You can visit this sample frontend we implemented for more details on how to integrate the SDK:

{% embed url="https://github.com/orbitalpay/orbitalpay-sdk/tree/main/merchant-example" %}

