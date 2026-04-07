# Trading Engine Overview

## Order Intake

When a user places an order, the backend validates it and routes it into the order flow.

- market
- side
- price
- size

## In-Memory Order Book

YOLO currently maintains an in-memory order-book store for active market state. It tracks:

- open orders
- bid and ask ladders
- top of book
- mid price
- matching state

## Matching and Resting

When an incoming order crosses the opposite side of the book, it can match against existing liquidity. If it does not fully cross, the remaining quantity can rest as an open order.

## Settlement Path

Filled activity then has to be settled into the underlying perp infrastructure. That settlement path connects:

- user-facing order execution
- onchain position state
- collateral and PnL accounting

## Positions and Margin Views

Account views such as:

- positions
- equity
- available margin
- maintenance buffer

## Why This Architecture Exists

YOLO needs both:

- an application-layer trading experience users can interact with quickly
- a deeper perp engine that tracks the actual market consequences
