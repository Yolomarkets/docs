# Perps Model

YOLO uses a hybrid perp model:

- the perp contracts live onchain
- the CLOB lives on the backend
- matched activity settles into the onchain system

## Onchain Perps

The critical market state lives onchain on Base.

That includes:

- collateral balances
- positions
- margin and health state
- settlement

This is the part that makes YOLO a real perp system rather than just a trading UI.

## Backend CLOB

The live order book is handled by the backend.

At a high level:

- users place orders through the app
- the backend stores and matches orders
- open orders rest in the backend CLOB until they are crossed or cancelled

This gives YOLO a fast order-book trading experience without putting the whole book onchain.

## How Orders Work

Orders enter the backend CLOB first.

If an order crosses the opposite side, it matches. If not, it rests on the book. Once matched, the backend builds settlement transactions and submits them into the onchain perp flow.

So the split is:

- matching happens in the backend
- final market state updates happen onchain

## Oracle Prices

The oracle price comes from the attention index.

That oracle price is pushed onchain and becomes the market reference price for the perp system. The order book can trade around it, but the system still has a reference anchor.

## Funding

Funding exists to keep the perp market connected to its reference price.

At a high level:

- if the live market drifts away from the oracle price
- funding helps create pressure back toward alignment

In YOLO, the backend also records recurring perp tick snapshots so the system can track the gap between the live market and the oracle price over time.

## Liquidations

Liquidations are part of the onchain perp system, not the backend CLOB.

The key idea is simple:

- users maintain positions with collateral
- the clearinghouse tracks account health
- if account health falls too far, the position can become liquidatable

So the backend handles trading flow, but liquidation risk is enforced by the onchain perp infrastructure.

## The Model in One Line

YOLO is a hybrid perp exchange:

- backend CLOB for speed
- onchain perps for final state
- attention index oracle for reference pricing
