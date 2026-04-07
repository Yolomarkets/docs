# Market Lifecycle

## 1. A Market Is Defined

Each market begins with a topic and product configuration:

- a market name
- a new product identifier
- a dedicated market book identity
- initial trading and risk parameters
- an associated image and metadata record

## 2. Market Assets and Metadata Are Stored

The stack stores:

- the market record in the application database
- uploaded market media through Pinata-backed storage
- creation metadata such as transaction references

## 3. A New Perp Product Is Created

YOLO creates a new perp market by:

- determining the next product ID
- deploying a unique virtual book contract identity
- registering the product with the perp engine

## 4. The Market Record Is Linked Back to the Product

Once the onchain product exists, the backend stores the mapping between:

- human-readable market name
- product ID
- virtual book identity
- chain metadata

## 5. The Initial Index Is Pushed

YOLO also triggers an initial attention-index refresh and pushes that reference price onchain so the market begins with an actual indexed state rather than an empty shell.

## Why This Matters

The result is a full tradable market object, not just a topic page.
