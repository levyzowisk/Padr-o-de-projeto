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

- Código deve ser escrito em inglês, seguindo os padrões de nomenclatura, exceto, rotas.

- Utilizar Snake_case para variáveis, model do prisma.

- Quando um coluna na tabela, tiver mais de uma palavra, devesse usar snake_case.

```
result_clients = Prisma.Client.findMany()

model Client_address {
  id Int @id @default(autoincrement())
  client_id Int
  address_id Int
  address Address @relation(fields: [address_id],references: [id], onDelete: Cascade)
  client Client @relation(fields: [client_id],references: [id],onDelete: Cascade)
  @@map("client_address");
}
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

 ## Padrões de rotas

 - As rotas devem ser escritas em português, representando os recursos no plural, conforme convenções RESTful.
 - Utilizar substantivos no plural para representar coleções de recursos.
 - Métodos HTTP devem indicar a ação a ser realizada.


 ```
 - GET /clientes: Retorna uma lista de clientes.
 - GET /clientes/:id: Retorna um cliente específico pelo ID.
 - POST /clientes: Cria um novo cliente.
 - PUT /clientes/:id: Atualiza os dados de um cliente existente pelo ID.
 - DELETE /clientes/:id: Remove um cliente pelo ID.
 ```



## Estrutura de código

- Route: Definem os endpoints da aplicação e mapeiam as requisições para a lógica que deve ser executada (geralmente através de controllers ou services).

- CONTROLLER: Cada controller deve ser responsável apenas por lidar com requisições HTTP e delegar responsabilidade como verificar campos e authenticação de users para o middleware.

- MIDDLEWARE: São funções que interceptam requisições e respostas, permitindo a manipulação e a implementação de funcionalidades que afetam o fluxo da aplicação

- REPOSITORY: Repositórios cuidam da interação com o banco de dados.

## Gerenciamento de Dependências

- NPM para gerenciamento de dependências
- 
