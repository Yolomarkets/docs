# How YOLO Works

YOLO Markets is a hybrid system with three core parts:

- perp contracts that live fully onchain
- a backend CLOB that handles the live order book
- an attention index that acts as the oracle price

## 1. Perps Live Onchain

The perp layer lives onchain on Base.

That is where the important market state ultimately exists:

- collateral balances
- positions
- risk and margin state
- settlement

The app is not pretending to be a perp exchange. It is a perp exchange, with the critical state anchored onchain.

## 2. The Order Book Is Hybrid

YOLO uses a hybrid CLOB model.

The CLOB lives on the backend, not fully onchain. That is what lets the product have a fast order-book trading experience.

At a high level:

- users place orders through the app
- the backend manages the order book and matches orders
- matched trades are then settled into the onchain perp system

So the backend handles speed and matching, while the onchain contracts handle final market state.

## 3. The Attention Index Is the Oracle Price

The attention index is the market reference price.

It is built from attention data, currently using:

- X/Twitter
- Google Trends

That signal is combined into an index and pushed onchain. In system terms, this is the oracle price for the market.

That price is what gives each topic market a reference anchor instead of leaving it as a free-floating order book.

## The Whole System in One Line

YOLO Markets is:

- onchain perps for real market state
- a backend CLOB for speed and matching
- an attention index oracle for market pricing
