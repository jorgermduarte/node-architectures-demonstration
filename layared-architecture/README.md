```
src/
├── controllers/             <-- Presentation layer (handles HTTP requests)
│   └── UserController.ts
│
├── services/                <-- Application layer (business logic)
│   └── UserService.ts
│
├── repositories/            <-- Data access layer (DB interaction)
│   └── UserRepository.ts
│
├── models/                  <-- Data models (ORM schema or interfaces)
│   └── UserModel.ts
│
├── dtos/                    <-- Data Transfer Objects
│   ├── CreateUserDTO.ts
│   └── UserResponseDTO.ts
│
├── mappers/                 <-- Transforms between DTOs, models, entities
│   └── UserMapper.ts
│
├── routes/                  <-- Express routing definitions
│   └── userRoutes.ts
│
├── config/                  <-- Configuration (e.g., DB connection)
│   └── db.ts
│
├── index.ts                 <-- Application entry point (Express setup)
└── tsconfig.json
```

```
Client HTTP Request
  ↓
Controller (input validation, routes)
  ↓
Service (business logic and orchestration)
  ↓
Repository (data fetching and saving)
  ↓
Model (persistent structure)
```