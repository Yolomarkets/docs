# Attention Index Overview

The attention index is one of the defining pieces of YOLO Markets.

It is the system that turns topic-level internet signal into a market reference price.

## What the Index Is For

The index is not meant to be a vague popularity score. It exists to give each market a reference value that the rest of the trading system can use.

In practical terms, the attention index helps:

- anchor the market around a topic signal
- power index charts
- create a reference for funding behavior
- connect narrative data to a tradable market

## Current Inputs

In the current implementation, the index is built from two main sources:

- X/Twitter activity
- Google Trends data

These are intentionally different kinds of signal:

- X captures live discourse and engagement
- Google Trends captures broader search interest

Together, they provide a more grounded view than either source alone.

## How It Is Combined

YOLO combines these sources into a weighted market signal and smooths that signal over time.

The important user-level understanding is:

- fresh attention data matters
- the system does not blindly snap to every short-lived spike
- the output becomes a continuous market reference

The exact formulas are intentionally out of scope for this documentation. What matters is the architecture and behavior, not reproducing the scoring math.

## Refresh Cadence

The attention index refresh job runs on a recurring UTC schedule and currently updates on a five-minute cadence.

That means the system is regularly re-evaluating each market's signal, not treating the index as a one-time setup value.

## What Happens After Refresh

Once the combined index is computed, YOLO pushes the resulting price onchain through its transaction flow.

That turns internet signal into something the perp market can actually reference.

## Why It Matters to Traders

For traders, the index matters because it is the market anchor.

It shapes:

- how the market is interpreted
- how funding is understood
- how the live tradable price can be compared to a reference

Without the attention index, the product would only be an order book around a topic. With it, YOLO becomes a structured market around that topic.
