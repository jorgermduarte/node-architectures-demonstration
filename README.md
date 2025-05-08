# 🏗️ Node.js Architecture Examples

This repository contains multiple examples of how to structure a Node.js + TypeScript backend using different software architecture styles. Each folder is a fully working (or scaffolded) project demonstrating a specific architectural approach.

---

## 🧱 Architectures Included

| Architecture Type         | Description                                                                 | Folder             |
|---------------------------|-----------------------------------------------------------------------------|---------------------|
| **Clean Architecture**    | Use cases in application layer, domain core decoupled from frameworks.      | `clean-architecture/` |
| **Hexagonal Architecture**| Ports & Adapters model. Input/output isolation.                             | `hexagonal-architecture/` |
| **Layered Architecture**  | Classic N-tier: Controller → Service → Repository.                          | `layered-architecture/` |
| **Onion Architecture**    | Concentric layers around domain with strict dependency direction.           | `onion-architecture/` |
| **Event-Driven (CQRS/ES)**| Commands/events separation, with optional event sourcing.                   | `event-driven/`  |

---

## 📁 Folder Structure

```
node-architectures-demonstration/
├── clean-architecture/
├── hexagonal-architecture/
├── layered-architecture/
├── onion-architecture/
├── event-driven/
└── README.md
```
