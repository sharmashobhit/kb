> Right architecture is all about Picking the right battles and managing the trade-offs.

# Clarifying the scope of the problem
System design is objective. A problem has multiple ways of approaching. However, one of the most important steps is to understand the requirements correctly.

- **Use cases**
	- Intended audience
	- Audience scopes and distinction
- **Constraints**
    - Identify the **traffic and data handling** constraints of the system in discussion
    - Scale of the system such as requests per second, requests types, data written per second, data read per second)
    - Special system requirements such as multi-threading, read or write oriented.