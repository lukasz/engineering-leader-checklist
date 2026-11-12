# Infrastructure 🛣️

[The Engineering Leader’s Checklist](../../README.md) -> [Technology 🦾](../technology.md)

This is all the platforms and processes required to run your product/service in production and provide the development and testing environments to the development team (which does not need to be a separate team and own this function on its own).

### Checklist
- **Provisioning / IaaS** / Physical servers (in rare cases nowadays) - all the servers and services needed to develop, test and run the products/services, like HTTP servers, databases, VCS, networking, caching, security, etc., in the following clusters
  - **Developer environments** - for the developers
  - **Staging** - meant for testing
  - **Production** - meant for end users 
- **CI/CD** - tooling and processes for automated (or semi-automated) deployment of the software to various environments, with the ability of automated testing and restoring. 
- **Disaster recovery** - what happens in case of a serious outage when your infrastructure is permanently damaged or lost (e.g. a data centre burns down, etc.) - e.g. keeping a redundant infrastructure in multiple physical locations. 
- **Backups** 
- **SLA** - including not just a secure infrastructure from the perspective of tech (disaster recovery, backups etc.) but also on-call engineers who can cover 24/7 availability of the system/product. 


### Related Cards
- [Architecture 🏛️](architecture.md)
- [Delivery 🚚](../delivery.md)
- On-call
