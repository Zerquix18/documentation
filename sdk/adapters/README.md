---
description: 'Reference, integration, and usage information for adapters and transports.'
---

# Adapters

**Adapters** are what connect the messy world of external data sources for different protocols \(blockchain, IPFS, web2 APIs, etc\) into the normalized world of the Governance SDK.

**Adapter Interfaces** define standardized units of composable governance functionality. Each adapter interface handles a single, focused area of responsibility such as interacting with [proposals](proposals-adapter.md) or querying [treasury](treasury-adapter.md) information.

Adapter Interfaces can be implemented by **Adapter Implementations** that each protocol must announce during protocol registration. A protocol can implement several adapters, even multiple instances of the same type.

Adapter responses are validated at run-time to ensure the implementation is correctly adhering to the spec defined by the SDK. This mapping logic can be tested by writing unit tests with mocked transports.

While a protocol can always implement an adapter from scratch to handle any custom mapping logic, often times it can simply use one of the SDK's provided [Governance Frameworks](../governance-frameworks/) that implement adapters for most of the common use cases.

{% hint style="info" %}
A Governance SDK protocol integration is composed of one or more adapter implementations that map downstream datasources and interactions into a standardized interface.
{% endhint %}

## Transports

Adapter implementations are the only part of the Governance SDK stack that directly interact with downstream datasources. Transport interfaces are defined by the SDK, which also ships standard implementations that can be used. Custom transport implementations can be passed to the SDK during instantiation to override their behavior

The following transports are passed to the protocol registration function and should be used when accessing external resources to facilitate testing and ensure external requests happen in a standardized way

* `ipfs` - Request files from the IPFS network
* `jsonRpc` - Interact an Ethereum-compatable blockchain over an RPC node
* `http` - Make standard HTTP requests
* `graph` - Make GraphQL requests \(over HTTP\)

{% hint style="info" %}
The TypeScript interfaces for all transport types can found here: **TODO**.
{% endhint %}
