# Collateral and Beta Account Model

This page explains how beta account funding works on YOLO Markets.

## The Role of `yCash`

In the current beta, `yCash` is the collateral users trade with.

From a product perspective, that means:

- it is the balance users are funded with
- it backs the beta trading experience
- it is the collateral basis for margin and positions

The goal is not to make users solve infrastructure before they can understand the product.

## Automatic Funding During Beta

YOLO currently automates part of the onboarding path by funding users with beta collateral.

In practice, the backend checks the user's account state and can top up the trading account automatically when the available collateral is below the beta threshold.

This is a deliberate beta design choice. It shortens time-to-first-trade and keeps product learning friction low.

## Wallet, Subaccount, and Trading Balance

Behind the scenes, the system maps the authenticated wallet into a trading subaccount model.

The important idea is:

- the wallet is the identity surface
- the subaccount is the trading surface
- the collateral balance is what supports margin usage and positions

Users do not need to manage these layers manually to understand the product, but the distinction matters for how the system is built.

## Why This Is Called a Beta Account Model

This page is framed as a beta account model because the current UX is intentionally opinionated:

- easier onboarding
- auto-funded collateral
- fewer manual setup steps

It is the right model for learning and iteration, but it should not be confused with the final product assumptions the team may choose later.
