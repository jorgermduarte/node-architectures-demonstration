```
src/
├── ports/
│   ├── in/
│   │   └── controllers/
│   │       └── UserControllerPort.ts
│   └── out/
│   │   └── repositories/
│   │       └── UserRepositoryPort.ts
│
├── adapters/
│   ├── in/
│   │   └── web/
│   │       ├── controllers/
│   │       │   └── UserController.ts
│   │       │   └── dto/
│   │       │   │   ├── CreateUserRequestDTO.ts
│   │       │   │   └── UserResponseDTO.ts
│   │       │   └── mapper/
│   │       │   │   └── UserWebMapper.ts           UserControllerPort <---> UserUseCasePort
│   │       └── routes/                        <--- Specific of Node!
│   │           └── userRoutes.ts              <--- Specific of Node!
│   │
│   └── out/
│       └── persistence/
|           └── models/
│               └── UserModel.ts               <-- Specific Implementation of a Domain Entity.
|           └── repositories/
│               └── UserRepository.ts          <-- Implementation of the UserRepositoryPort
│           └── db.ts                          <-- Specific of Node!
│
├── domain/                                    <-- Invariant business logic (entities, business rules, value objects)
│   └── entities/
│   │   └── User.ts
│
├── application/                              <-- Orchestration logic
│   └── usecases/
│   │   └── ports/
│   │       └── UserUseCasePort.ts
│   │   ├── UserUseCase.ts
│   │   └── mapper/
│   │     └── UserMapper.ts                  UserUseCasePort <---> UserRepositoryPort
│   │   └── dto/
│   │   │   │   ├── CreateUserDTO.ts             <-- Specific dtos used on the use case
│   │   │   │   └── UserResultDTO.ts             <-- Specific dtos used on the use case
│
├── index.ts                                   <--- Specific of Node!
├── tsconfig.json                              <--- Specific of Node!
└── package.json                               <--- Specific of Node!
```


```
HTTP Request
  ↓
UserController (Adapter In)
  ↓ implements
UserControllerPort (Port In)
  ↓ calls
UserUseCase (Domain UseCase)
  ↓ implements
UserUseCasePort (Port In)
  ↓ calls
UserRepository (Adapter Out)
  ↓ implements
UserRepositoryPort (Port Out)
```