# Collateral and Beta Account Model

This page explains how beta account funding works on YOLO Markets.

## The Role of `yCash`

In the current beta, `yCash` is the collateral users trade with.

- it is the balance users are funded with
- it backs the beta trading experience
- it is the collateral basis for margin and positions

## Automatic Funding During Beta

YOLO automates part of onboarding by funding users with beta collateral and topping up the account when needed.

## Wallet, Subaccount, and Trading Balance

Behind the scenes:

- the wallet is the identity surface
- the subaccount is the trading surface
- the collateral balance is what supports margin usage and positions

## Why This Is Called a Beta Account Model

This is called a beta account model because the UX is intentionally opinionated:

- easier onboarding
- auto-funded collateral
