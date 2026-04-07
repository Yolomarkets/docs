# Pricing and Market Data

YOLO Markets exposes more than one price because each price answers a different question.

## The Key Price Types

### Index Price

The index price is the reference value derived from the attention-index pipeline.

### Mid Price

The mid price is derived from the order book.

## Why These Prices Both Matter

They tell users different things:

- the index tells you what the system considers the topic's reference price
- the mid tells you where live trading interest is meeting in the market

## Snapshots and Charts

YOLO stores market-price snapshots over time and uses them to build charts for:

- index price
- mid price

## What This Means for Users

When a user sees price data on YOLO, the right questions are:

- is this the reference price or the tradable market price?
- are they aligned?
- if not, why not?
