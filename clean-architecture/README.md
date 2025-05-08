src/
├── domain/
│   ├── entities/
│   │   └── User.ts                      <-- Business rules (pure logic)
│   ├── value-objects/
│   │   └── Email.ts                    <-- Strongly typed core values
│   └── repositories/
│       └── IUserRepository.ts       <-- (interface to DB)
│
├── application/
│   └── usecases/
│       ├── dto/
│       │   ├── CreateUserCommand.ts    <-- Input for use case
│       │   └── UserResult.ts           <-- Output of use case
│       ├── interfaces/
│       │   └── ICreateUserUseCase.ts <-- Input  (interface for use case)
│       ├── mappers/
│       │   └── UserMapper.ts           <-- Domain ↔ DTO conversion
│       └── CreateUserUseCase.ts        <-- Business use case logic
│
├── infrastructure/
│   ├── web/
│   │   ├── controllers/
│   │   │   └── UserController.ts       <-- Handles requests, calls use case
│   │   ├── dto/
│   │   │   ├── CreateUserRequestDTO.ts
│   │   │   └── UserResponseDTO.ts
│   │   ├── mappers/
│   │   │   └── UserWebMapper.ts        <-- DTO ↔ Use case command/result
│   │   └── routes/
│   │       └── userRoutes.ts           <-- Express routes
│   │
│   └── persistence/
│       ├── models/
│       │   └── UserModel.ts            <-- ORM schema (e.g., Prisma, TypeORM)
│       ├── repositories/
│       │   └── UserRepository.ts       <-- Implements UserRepositoryPort
│       └── db.ts                       <-- Database connection setup
│
├── config/
│   └── container.ts                    <-- Dependency injection setup
├── index.ts                            <-- Application entry point
├── tsconfig.json
└── package.json
