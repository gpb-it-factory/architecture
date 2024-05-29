```text
# Пример структуры проекта (вариант 4)

Пример структуры проекта, использующего "Чистую архитектуру" (но это не точно) с разделением по фичам.
Не переиспользуются код из других модулей. Весь нужный код содержится в модуле.
Да, даже модели, репозитории и т. д.

```text
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── ru/
│   │   │   │   ├── gazprombank/
│   │   │   │   │   ├── example/
│   │   │   │   │   │   ├── features/
│   │   │   │   │   │   │   ├── register/
│   │   │   │   │   │   │   │   ├── application/
│   │   │   │   │   │   │   │   │   ├── RegisterUserUseCase.java
│   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   ├── UserRegistrationRequest.java
│   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   ├── User.java
│   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   ├── UserRepository.java
│   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   ├── UserService.java
│   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   ├── JpaUserRepository.java
│   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   ├── UserController.java
│   │   │   │   │   │   │   │   ├── createaccount/
│   │   │   │   │   │   │   │   │   ├── application/
│   │   │   │   │   │   │   │   │   │   ├── CreateAccountUseCase.java
│   │   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   │   ├── CreateAccountRequest.java
│   │   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   │   ├── Account.java
│   │   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountRepository.java
│   │   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountService.java
│   │   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   │   ├── JpaAccountRepository.java
│   │   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountController.java
│   │   │   │   │   │   │   │   ├── getbalance/
│   │   │   │   │   │   │   │   │   ├── application/
│   │   │   │   │   │   │   │   │   │   ├── GetAccountBalanceUseCase.java
│   │   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountBalanceResponse.java
│   │   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   │   ├── Account.java
│   │   │   │   │   │   │   │   │   │   │   ├── Balance.java
│   │   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountRepository.java
│   │   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountBalanceService.java
│   │   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   │   ├── JpaAccountBalanceRepository.java
│   │   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   │   ├── AccountBalanceController.java
│   │   │   │   │   │   │   │   ├── transfermoney/
│   │   │   │   │   │   │   │   │   ├── application/
│   │   │   │   │   │   │   │   │   │   ├── TransferMoneyUseCase.java
│   │   │   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   │   │   ├── TransferMoneyRequest.java
│   │   │   │   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   │   │   │   ├── Transfer.java
│   │   │   │   │   │   │   │   │   │   │   ├── Account.java
│   │   │   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   │   │   ├── TransferRepository.java
│   │   │   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   │   │   ├── TransferService.java
│   │   │   │   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   │   │   │   ├── JpaTransferRepository.java
│   │   │   │   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   │   │   │   ├── TransferController.java
│   │   │   │   │   │   │   ├── configuration/
│   │   │   │   │   │   │   │   ├── AppConfig.java
```

Плюсы:
- наибольшая модульность и связность из всех предыдущих подходов;
- легко понять фичу без контекста всего проекта - весь код в рамках модуля;

- Минусы:
- дублирование кода - какой-то код точно будет повторяться; 
- нетривиальная реализация при сложной структуре БД.  