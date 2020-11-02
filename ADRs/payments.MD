# Use of asynchronous payment service

## Status
_PROPOSED_

## Context
Implementing payment service in synchronous or asynchronous? Assuming we will be using a 3rd party payment provider.

## Decision
To implement payment service as asynchronous. Here is an overview of asynchronous payment flow:
- The service receives a payment request
- Validate the request, produce/publish a transaction then send a success response to the client  
- Once a transaction is produced a consumer service will make an actual transaction with the 3rd party payment provider
- In case of failure, the transaction is pushed to a failed queue so the consumer can retry the transaction (according to a configurable retention policy).

## Consequences
Main advantages:
- Remove direct dependency on 3rd party payment providers
- **Lower latency**. Respond to the client without having to wait for the payment provider transaction to be successful
- **No Downtime**. If the payment provider wants a planned routine downtime, the system will still accept payments and produce them to the payment provider once it's available again
- **Retention**. Retry transactions internally (Failure queue), for example: payment provider is unavailable 
- **Scalability and Availability**. Scale/Replicate the system according to your needs regardless of the payment provider's architecture