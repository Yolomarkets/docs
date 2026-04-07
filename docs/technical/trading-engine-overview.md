# Trading Engine Overview

This page explains how a user action turns into a live market action inside YOLO Markets.

## Order Intake

When a user places an order, the backend validates the order and routes it into the product's order flow.

At a high level, an order includes:

- market
- side
- price
- size

From there, the system decides whether the order should execute immediately or rest on the book.

## In-Memory Order Book

YOLO currently maintains an in-memory order-book store for active market state.

That store keeps track of:

- open orders
- bid and ask ladders
- top of book
- mid price
- matching state

This is what gives the product a responsive order-book trading experience.

## Matching and Resting

When an incoming order crosses the opposite side of the book, it can match against existing liquidity. If it does not fully cross, the remaining quantity can rest as an open order.

This creates the familiar maker/taker style market behavior users expect from an order-book venue.

## Settlement Path

Matching is not the end of the story. Filled activity then has to be settled into the underlying perp infrastructure.

That settlement path is what connects:

- user-facing order execution
- onchain position state
- collateral and PnL accounting

In other words, the order book is the front half of trading. Settlement is the back half that makes it real.

## Positions and Margin Views

Account views such as:

- positions
- equity
- available margin
- maintenance buffer

are derived from the underlying perp and clearinghouse state, then translated into product-facing output.

## Why This Architecture Exists

YOLO needs both:

- an application-layer trading experience users can interact with quickly
- a deeper perp engine that tracks the actual market consequences

That is why the trading engine should be understood as a coordinated system, not a single component.
