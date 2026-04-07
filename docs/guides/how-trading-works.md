# How Trading Works

YOLO Markets gives users a familiar long/short trading interface, but the markets themselves are built around topics and narratives rather than traditional tickers.

## Long and Short

The core action is straightforward:

- go long if you think a market will strengthen
- go short if you think it will weaken

You are expressing directional conviction on a live topic market.

## Orders

Trading happens through an order-book model.

That means users place orders at chosen prices and sizes, and those orders either:

- match against existing liquidity
- rest on the book until another order crosses them

This gives the product a real trading surface rather than a simple instant-conversion interface.

## Fills and Positions

When orders match, they create fills and update positions.

From the user's point of view, the important outputs are:

- position size
- entry exposure
- unrealized PnL
- margin usage

Once a position exists, it continues to move with the market until it is reduced, flipped, or closed.

## PnL

PnL changes as the market moves relative to the user's position.

Long positions benefit when the market moves in their favor. Short positions benefit when the market moves the other way.

Because these are perp-style markets, PnL is part of a broader margin system rather than a one-time settlement event.

## What Makes Trading Here Different

The trading mechanics are familiar, but the underlying market behavior is different because the driver is narrative and attention.

That means the product sits at the intersection of:

- order-book trading
- perp-style exposure
- internet-native market behavior

Users should expect the mechanics to feel tradable and structured, while the market itself remains fast, cultural, and highly reflexive.
