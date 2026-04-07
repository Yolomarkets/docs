# Points and Leaderboard Mechanics

The points system on YOLO is not just a cosmetic badge layer. It is a tracked product mechanism with its own data flow.

## Points as a System

At a high level, the system does three things:

- records eligible reward events from trading activity
- stores points history for users
- materializes a leaderboard from that activity

This is what turns "points" from a vague engagement idea into an actual product feature.

## Where Points Come From

In the current implementation, points are tied to trading activity rather than passive account existence.

That means the system observes market participation, creates reward events, and records those events into reward history.

The exact formula is intentionally not the focus of this documentation. The right architectural takeaway is:

- trading activity leads to reward events
- reward events lead to points history
- points history feeds ranking

## Leaderboard Layer

The leaderboard is built as a dedicated view over user activity and stored reward history.

From a product standpoint, that gives YOLO:

- visible ranking
- account-level point totals
- volume-aware participation views

The leaderboard is refreshed on a recurring cadence so the ranking stays current without forcing every product screen to recompute the full standings from scratch.

## Why This Matters in Beta

The points and leaderboard system matters because it changes behavior.

It gives users:

- a reason to come back
- a way to compare activity
- a stronger sense of progression

But the intended framing remains disciplined: points are part of the current product loop, not a guarantee about future external rewards.
