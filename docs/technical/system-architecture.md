# System Architecture

This page explains YOLO Markets as a system rather than just a trading interface.

## The High-Level Shape

At a high level, YOLO has four major layers:

- the product interface users trade through
- backend services that manage market state and product workflows
- storage and indexing layers for market and user data
- onchain perp infrastructure on Base

Each layer has a different job.

## Product Layer

The product layer is what users see:

- market pages
- charts
- order entry
- positions and PnL views
- points and leaderboard surfaces

This is where the trading experience is presented, but it is not where the core market mechanics live.

## Backend Layer

The backend is the coordination layer.

It handles responsibilities such as:

- market creation and listing
- user login and beta onboarding behavior
- order intake and order-book management
- fetching positions and account stats
- computing attention inputs
- pushing updated index values onchain
- managing points and leaderboard refreshes

This is also where product-facing abstractions are created from lower-level contract and database state.

## Storage Layer

YOLO stores structured product data offchain for speed, visibility, and queryability.

That includes:

- market records and metadata
- order and settlement history
- attention index runs
- tweet snapshots for source context
- chart snapshots and price history
- reward history and leaderboard materialization

Market media and metadata also flow through external storage, including uploaded market assets.

## Onchain Layer

The onchain layer is the perp infrastructure on Base.

It includes contracts for:

- endpoint and sequenced transaction handling
- perp engine state
- spot and collateral balances
- clearinghouse and risk views
- exchange-level fee collection and settlement support

This layer is where collateral, positions, risk state, and market-level reference values ultimately matter.

## What Lives Offchain vs Onchain

The simplest way to think about the split is:

- offchain: product orchestration, discovery, indexing, charts, and fast application logic
- onchain: collateral, market state, risk-critical accounting, and reference price writes

YOLO uses both because the product needs the speed and flexibility of an app layer, while still anchoring core trading state to onchain perp infrastructure.
