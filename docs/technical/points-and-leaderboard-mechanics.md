# Points and Leaderboard Mechanics

The points system on YOLO is a tracked product mechanism with its own data flow.

## Points as a System

- records eligible reward events from trading activity
- stores points history for users
- materializes a leaderboard from that activity

## Where Points Come From

In the current implementation, points are tied to trading activity.

- trading activity leads to reward events
- reward events lead to points history
- points history feeds ranking

## Leaderboard Layer

The leaderboard is built as a dedicated view over user activity and stored reward history. It gives YOLO:

- visible ranking
- account-level point totals
- volume-aware participation views

## Why This Matters in Beta

It gives users:

- a reason to come back
- a way to compare activity
- a stronger sense of progression
