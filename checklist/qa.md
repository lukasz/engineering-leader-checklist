# QA 🔍

[The Engineering Leader’s Checklist](../README.md)

## Checklist
- **Automated Testing** - various levels of abstraction
  - **Static code analysis** - pre-commit at developer’s level - very good practice! 
  - **Unit** - most basic and important to cover - TDD approach recommended! 
  - **Integration** - one level of abstraction above Unit tests - they complement Unit tests like nothing else! 
  - **E2E** - End-to-end testing - most complex and prone to errors and false positives. Not always needed - due to the cost of implementation and maintenance, should be used with caution when really needed. 
  - **Contract** - helps a lot in more complex systems, when more than one system needs to cooperate - not only to test but also to unblock certain bottlenecks between teams (if one team exposes a contract test suite for the other one, the other one can start developing against it, even if the actual system is not finished) 
- **Manual QA** 

### Related cards
- [Product Engineering 📲](product-engineering.md)

---
V2

### Books

### Resources

### Tools
