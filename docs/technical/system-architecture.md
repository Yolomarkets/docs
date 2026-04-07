# System Architecture

## The High-Level Shape

At a high level, YOLO has four major layers:

- the product interface users trade through
- backend services that manage market state and product workflows
- storage and indexing layers for market and user data
- onchain perp infrastructure on Base

## Product Layer

The product layer is what users see:

- market pages
- charts
- order entry
- positions and PnL views
- points and leaderboard surfaces

## Backend Layer

The backend handles:

- market creation and listing
- user login and beta onboarding behavior
- order intake and order-book management
- fetching positions and account stats
- computing attention inputs
- pushing updated index values onchain
- managing points and leaderboard refreshes

## Storage Layer

Offchain storage includes:

- market records and metadata
- order and settlement history
- attention index runs
- tweet snapshots for source context
- chart snapshots and price history
- reward history and leaderboard materialization

## Onchain Layer

The onchain layer on Base includes contracts for:

- endpoint and sequenced transaction handling
- perp engine state
- spot and collateral balances
- clearinghouse and risk views
- exchange-level fee collection and settlement support

## What Lives Offchain vs Onchain

- offchain: product orchestration, discovery, indexing, charts, and fast application logic
- onchain: collateral, market state, risk-critical accounting, and reference price writes
