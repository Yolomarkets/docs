# Market Lifecycle

This page explains what happens when a new YOLO market is created.

## 1. A Market Is Defined

Each market begins with a topic and product configuration.

At a high level, creation includes:

- a market name
- a new product identifier
- a dedicated market book identity
- initial trading and risk parameters
- an associated image and metadata record

## 2. Market Assets and Metadata Are Stored

When a market is created, the product stores both structured metadata and media.

The current stack persists:

- the market record in the application database
- uploaded market media through Pinata-backed storage
- creation metadata such as transaction references and related contract context

This allows the market to exist as both a user-facing object and a technical trading object.

## 3. A New Perp Product Is Created

Behind the scenes, YOLO creates a new perp market by:

- determining the next product ID
- deploying a unique virtual book contract identity
- registering the product with the perp engine

Users do not need the low-level contract details, but the key idea is that every market becomes a real perp product in the underlying trading system.

## 4. The Market Record Is Linked Back to the Product

Once the onchain product exists, the backend stores the mapping between:

- human-readable market name
- product ID
- virtual book identity
- chain metadata

That is what lets the product layer display the market while still talking to the right onchain system underneath.

## 5. The Initial Index Is Pushed

Market creation does not stop at registration.

YOLO also triggers an initial attention-index refresh and pushes that reference price onchain so the market begins with an actual indexed state rather than an empty shell.

## Why This Matters

The market lifecycle shows what YOLO is really building:

- not just pages for topics
- not just a database of names
- but full tradable market objects with metadata, pricing context, and perp-engine presence

That is the bridge between product narrative and real market infrastructure.
