# Пример структуры проекта (вариант 3)

Пример структуры проекта, использующего "Чистую архитектуру", но с разделением по фичам.
Во избежание дублирования мы переиспользуем абстракции из других пакетов.

**ТАК ДЕЛАТЬ НЕЛЬЗЯ, не используйте такой подход**

```text
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── ru/
│   │   │   │   ├── gazprombank/
│   │   │   │   │   ├── example/
│   │   │   │   │   │   ├── features/
│   │   │   │   │   │   │   ├── register/
│   │   │   │   │   │   │   │   ├── RegisterUserUseCase.java
│   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   ├── UserRegistrationRequest.java
│   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   ├── User.java
│   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   ├── UserRepository.java
│   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   ├── UserService.java
│   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   ├── JpaUserRepository.java
│   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   ├── UserController.java
│   │   │   │   │   │   │   │   ├── createaccount/
│   │   │   │   │   │   │   │   │   ├── CreateAccountUseCase.java
│   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   ├── CreateAccountRequest.java
│   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   ├── Account.java
│   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   ├── AccountRepository.java
│   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   ├── AccountService.java
│   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   ├── JpaAccountRepository.java
│   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   ├── AccountController.java
│   │   │   │   │   │   │   │   ├── getbalance/
│   │   │   │   │   │   │   │   │   ├── GetAccountBalanceUseCase.java
│   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   ├── AccountBalanceResponse.java
│   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   ├── Balance.java
│   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   ├── AccountBalanceRepository.java
│   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   ├── AccountBalanceService.java
│   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   ├── JpaAccountBalanceRepository.java
│   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   ├── AccountBalanceController.java
│   │   │   │   │   │   │   │   ├── transfermoney/
│   │   │   │   │   │   │   │   │   ├── TransferMoneyUseCase.java
│   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   ├── TransferMoneyRequest.java
│   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   ├── Transfer.java
│   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   ├── TransferRepository.java
│   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   ├── TransferService.java
│   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   ├── JpaTransferRepository.java
│   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   ├── TransferController.java
│   │   │   │   │   │   │   ├── configuration/
│   │   │   │   │   │   │   │   ├── AppConfig.java
```

Минусы очевидны - пытаясь увеличить связность и модульность, мы создали лишние связи, что противоречит цели - никакой модульности нет, а код стал ещё более запутанным - появились 
нелогичные связи между пакетами, которые не видны с первого взгляда на структуру проекта.    

