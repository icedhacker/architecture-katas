# Monolithic Architecture

## Status
_REJECTED_

## Context

Microservices have been around for some while, and are a pretty well known pattern to build applications and digital services, but are they always the best pattern to go with.

On the other hand a Monolith isn’t a dated architecture that we need to leave in the past. In certain circumstances, a monolith is ideal.

Monolithic architecture has some distinct pros:
- Easier to develop and start with
- Easier to test
- Simpler to deploy
- Simpler to scale horizontally
- No major learning curve needed here

However there might also be some cons:
- Application becomes relatively large with time
- Application growth means more complexity and slower start up time
- Deployment of whole app with every update
- Testing effort is higher with updates
- CD is difficult
- Harder to scale
- Harder to adopt new technologies
- One bug might lead to the whole app being down

For the use case we have and for the business as a whole, adopting a monolithic architecture might still be a good pattern to consider. 
The business size might not be huge for Microservices to be considered. It would just slow down the development of the solution and getting the system live. Also maintaining a huge number of services means more effort and cost that might not be worth it at the end.

## Decision

Monolithic architecture wasn't the best architecture to go with and the team found out that Serverless architecture would be a better fit to the business case.
Please refer to the Serverless ADR for more info.
