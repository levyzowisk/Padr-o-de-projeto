# Padronização do Back-End

## Nomenclatura de arquivos e Pastas

### Arquivos

- Usar nomes descritivos e seguir um padrão consistente, como camelCase para arquivos JavaScript ou PascalCase para arquivos que exportam classes.

- Arquivos que exportam classes, o ideal é que começe com letra maiúscula(PascalCase) 
```
/src
 /controllers
  - ClientController
```  

### Pastas

- Usar nomes no plural para pastas(CAMEL_CASE) (ex.: controllers, models, services).

```
/src
  /userController
  /authMiddleware
  /userModel
  /paymentService
```

 
## Padrões de código

- Utilizar Snake_case para variáveis, model do prisma.

```
result_clients = Prisma.Client.findMany()
```

- Funções (camelCase)
```
createClient() {}
```

- Classes(PascalCase)

```
class ClientRepository()
 {

 }
 ```

## Estrutura de código

- Route: Definem os endpoints da aplicação e mapeiam as requisições para a lógica que deve ser executada (geralmente através de controllers ou services).

- CONTROLLER: Cada controller deve ser responsável apenas por lidar com requisições HTTP e delegar responsabilidade como verificar campos e authenticação de users para o middleware.

- MIDDLEWARE: São funções que interceptam requisições e respostas, permitindo a manipulação e a implementação de funcionalidades que afetam o fluxo da aplicação

- REPOSITORY: Repositórios cuidam da interação com o banco de dados.

## Gerenciamento de Dependências
- NPM para gerenciamento de dependências
