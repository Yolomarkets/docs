# Attention Index Overview

The attention index turns topic-level internet signal into a market reference price.

## What the Index Is For

It helps:

- anchor the market around a topic signal
- power index charts
- create a reference for funding behavior

## Current Inputs

The current index uses:

- X/Twitter activity
- Google Trends data

## How It Is Combined

YOLO combines these sources into a weighted, smoothed market signal.

- fresh attention data matters
- the system does not blindly snap to every short-lived spike

## Refresh Cadence

The attention index refresh job runs on a recurring UTC schedule and currently updates on a five-minute cadence.

## What Happens After Refresh

Once the combined index is computed, YOLO pushes the resulting price onchain through its transaction flow.

## Why It Matters to Traders

For traders, the index matters because it is the market anchor.

- how the market is interpreted
- how funding is understood
- how the live tradable price can be compared to a reference
