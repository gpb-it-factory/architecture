# Пример структуры проекта (вариант 2)

Пример структуры проекта, использующего "Чистую архитектуру", но с разделением по крупным сущностям.

```text
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── ru/
│   │   │   │   ├── gazprombank/
│   │   │   │   │   ├── example/
│   │   │   │   │   │   ├── user/
│   │   │   │   │   │   │   ├── usecase/
│   │   │   │   │   │   │   │   ├── RegisterUserUseCase.java
│   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   ├── UserRegistrationRequest.java
│   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   ├── User.java
│   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   ├── UserService.java
│   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   ├── UserRepository.java
│   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   ├── JpaUserRepository.java
│   │   │   │   │   │   │   ├── rest/
│   │   │   │   │   │   │   │   ├── UserController.java
│   │   │   │   │   │   │   ├── configuration/
│   │   │   │   │   │   │   │   ├── UserConfig.java
│   │   │   │   │   │   ├── account/
│   │   │   │   │   │   │   ├── usecase/
│   │   │   │   │   │   │   │   ├── CreateAccountUseCase.java
│   │   │   │   │   │   │   │   ├── GetAccountBalanceUseCase.java
│   │   │   │   │   │   │   │   ├── TransferMoneyUseCase.java
│   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   ├── CreateAccountRequest.java
│   │   │   │   │   │   │   │   ├── TransferMoneyRequest.java
│   │   │   │   │   │   │   │   ├── AccountBalanceResponse.java
│   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   ├── Account.java
│   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   ├── AccountService.java
│   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   ├── AccountRepository.java
│   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   ├── JpaAccountRepository.java
│   │   │   │   │   │   │   ├── rest/
│   │   │   │   │   │   │   │   ├── AccountController.java
│   │   │   │   │   │   │   │   ├── TransferController.java
│   │   │   │   │   │   ├── configuration/
│   │   │   │   │   │   │   ├── Config.java
```

Плюсы:
- всё ещё соблюдаем архитектуру;
- улучшилась модульность - мы можем вынести пакет user в отдельный сервис "одним кликом";
- понимать приложение стало легче - по крайней понятны крупные направления, которыми занимается наше приложение. 

Минусы:
- всё ещё есть некоторая мешанина из классов, чтобы понять, что происходит на уровне фичи, придётся "погулять" по проекту;
- если внезапно нужна модульность на уровне юзкейса/фичи - такой подход нам не поможет. 

