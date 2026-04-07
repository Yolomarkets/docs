# Attention Index

The attention index is the reference price for each YOLO market.

## What It Does

The index gives every topic market an anchor price.

That matters because without it, the market would just be a floating order book. With it, the system has a market reference it can use for pricing and funding context.

## Inputs

The current index uses:

- X/Twitter
- Google Trends

X captures live discussion and engagement. Google Trends captures broader search interest. YOLO combines both into one market signal.

Coming soon, YOLO plans to expand the index with more attention sources such as:

- Reddit
- Instagram
- YouTube
- Facebook

## How It Is Used

At a system level, the attention index is the oracle price.

That means:

- the backend computes the index for each market
- the resulting price is pushed onchain
- the perp system treats that value as the market reference price

This is what turns internet attention into a usable market input.

## Refresh Cadence

The attention index updates on a recurring UTC schedule and currently refreshes every five minutes.

That keeps the market reference price live instead of static.

## Why It Exists

YOLO markets are built around topics, not traditional assets. The index is what makes those markets legible to the trading system.

In short:

- the topic creates the market
- the attention index creates the reference price
- the order book trades around that price
