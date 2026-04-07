# Pricing and Market Data

YOLO Markets exposes more than one price because each price answers a different question.

## The Key Price Types

### Index Price

The index price is the reference value derived from the attention-index pipeline. It is the market's anchor.

### Mid Price

The mid price is derived from the order book. It sits between the best bid and best ask when the market has valid two-sided liquidity.

This is the clearest high-level representation of where the live tradable market is sitting right now.

## Why These Prices Both Matter

The index and the mid are not redundant.

They tell users different things:

- the index tells you what the system considers the topic's reference price
- the mid tells you where live trading interest is meeting in the market

The gap between them is useful information. It reveals when the tradable market is leaning away from the underlying reference.

## Snapshots and Charts

YOLO stores market-price snapshots over time and uses them to build charts for both:

- index price
- mid price

This allows the product to show:

- trend over time
- short-term movement
- how live trading price compares with the reference price
- percentage change over common windows

## What This Means for Users

When a user sees price data on YOLO, the right question is not just "what is the price?"

It is:

- is this the reference price or the tradable market price?
- are they aligned?
- if not, why not?

That is the correct mental model for reading market data on a perp product built around narratives.
