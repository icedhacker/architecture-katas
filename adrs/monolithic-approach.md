# Monolithic Architecture

## Status
_REJECTED_

## Context

- Farmacy Food is at the inception phase and the target is to hit 1000 users by the end of this year, which will be initial load for the Farmacy food service.
- It will be needed to scale as the consumer base increases.
- The load will fluctuate with time of the day, around meal times the demand can be higher.

## Decision

Microservices have been around for some while, and are a pretty well known pattern to build applications and digital services, but are they always the best pattern to go with. On the other hand a Monolith isn’t a dated architecture that we need to leave in the past. In certain circumstances, a monolith is ideal.

All the system components will be implemented as a monolith with a single database.


## Consequences

Postives: 
- Easier to develop and start with, as there will be one single respository
- Easier to test as there is less integration points
- Simpler to deploy with one time configuration effort
- Simpler to scale vertically
- No major learning curve needed
- Simple monitoring with single instance and a single database

Negatives: 
- Application becomes relatively large with time
- Application growth means more complexity and slower start up time
- Deployment of whole app with every update
- Low level of elasticity in scaling
- Harder to adopt new technologies
- One bug might lead to the whole app being down

