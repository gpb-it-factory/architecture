# Пример структуры проекта (вариант 1)

Пример структуры проекта, использующего "Чистую архитектуру". 
Пакеты разделены строго по слоям.

```text
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── ru/
│   │   │   │   ├── gazprombank/
│   │   │   │   │   ├── example/
│   │   │   │   │   │   ├── application/
│   │   │   │   │   │   │   ├── usecases/
│   │   │   │   │   │   │   │   ├── RegisterUserUseCase.java
│   │   │   │   │   │   │   │   ├── CreateAccountUseCase.java
│   │   │   │   │   │   │   │   ├── GetAccountBalanceUseCase.java
│   │   │   │   │   │   │   │   ├── TransferMoneyUseCase.java
│   │   │   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   │   │   ├── UserRegistrationRequest.java
│   │   │   │   │   │   │   │   │   ├── CreateAccountRequest.java
│   │   │   │   │   │   │   │   │   ├── TransferMoneyRequest.java
│   │   │   │   │   │   │   │   │   ├── AccountBalanceResponse.java
│   │   │   │   │   │   │   ├── domain/
│   │   │   │   │   │   │   │   ├── User.java
│   │   │   │   │   │   │   │   ├── Account.java
│   │   │   │   │   │   │   │   ├── service/
│   │   │   │   │   │   │   │   │   ├── UserService.java
│   │   │   │   │   │   │   │   │   ├── AccountService.java
│   │   │   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   │   │   ├── UserRepository.java
│   │   │   │   │   │   │   │   │   ├── AccountRepository.java
│   │   │   │   │   │   │   ├── infrastructure/
│   │   │   │   │   │   │   │   ├── persistence/
│   │   │   │   │   │   │   │   │   ├── JpaUserRepository.java
│   │   │   │   │   │   │   │   │   ├── JpaAccountRepository.java
│   │   │   │   │   │   │   │   ├── configuration/
│   │   │   │   │   │   │   │   │   ├── AppConfig.java
│   │   │   │   │   │   │   ├── interfaces/
│   │   │   │   │   │   │   │   ├── rest/
│   │   │   │   │   │   │   │   │   ├── UserController.java
│   │   │   │   │   │   │   │   │   ├── AccountController.java
```

Плюсы: 
- чётко соблюдаем предписанную архитектуру;
- очень сложно напортачить со слоями - они зафиксированы на верхнем уровне;
- отсутствие какого-либо дублирования - вся конфигурация или инфраструктурный код принадлежит конкретному слою.

Минусы:
- с точки зрения структуры проекта - с модульностью большие проблемы;
- сложно представить весь сервис или "кусок" функциональности в голове, т. к. код, относящийся к единице
функциональности, в проекте раскидан по слоям.

Кстати, простой тест на модульность: можем ли мы взять модуль и перенести "одним кликом" в другой проект? (или вообще удалить!) 