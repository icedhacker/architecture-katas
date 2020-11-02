# Use of Serverless Architecture

## Status
_PROPOSED_

## Context
For a new business, having quick development cycles is vital in order to iterate by adjusting the target of the offer according to real customer needs. Focusing capitals and attention more to the main business and less to NFRs (deployment/maintanability/security) but delivering an elastic and scalable solution which doesn't need further costs/time for development and maintain a high available system are all key factor to success.

## Decision
To implement all required services as lambda function to run in a cloud based serverless solution like AWS lambda and use dynamo or a serverless Aurora if SQL is needed. In the future, if required by attacching a VPC to lambda we can reach RDS or elastic search servers too evolving a complete serverless solution to an hybrid solution in order to work around future cons that this architecture may have with a bigger business.

## Consequences
The main advantages are:
- it scales with demand automatically
- it significantly reduces server cost (70-90%), because you don’t pay for idle
- it eliminates server maintenance
- it frees up developer resources to take on projects that directly drive business value (versus spending that time on maintenance)
This solution comes with some issues also like:
- we don’t manage the server. That also means you lose control over server hardware, runtimes and runtime updates.
- The provider imposes concurrency and resource limits.
- cold startups means higher latencies. That can be mitigated by coding in quick to start apps like the ones coded in python or go more than Java or C#. Beside this we could keep warm the APIs.
- We could get easily locked-in the provider ecosystem. If this is seen as a real problem opting for a Kubernetes serveless (eg KNative) could be a solution.
