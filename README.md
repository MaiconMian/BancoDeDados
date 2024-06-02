## Criando o banco de dados

Para criação do banco de dados, o arquivo "produtos_db.sql" está disponível. Basta acessar o mysql:
```sh
    mysql -u root -p
```
(caso tenha deixado padrão, use o sudo antes de cada iteração)
após isso, basta executar o comando:
```sh
    create DATABASE produtos_jdbc;
``` 
e em seguida dar EXIT para sair.

Após isso, basta ir ao diretorio do arquivo "produtos_db.sql" e executar o seguinte comando:
```sh
    mysql -u root -p produtos_jdbc < produtos_db.sql
``` 
pronto, o banco de dados foi criado para o usuário root.

## Criando o usuário para conexão

Para acessar o banco de dados pelo código, é necessário criar um usuário com as seguintes 
características:
```sh
    USER: 'Adiministrador'
    SENHA: 'Secret_123'
``` 
Para realizar isso, siga os passos (com o banco de dados já criado) e dentro do Mysql no modo root:
```sh
    CREATE USER 'Adiministrador'@'localhost' IDENTIFIED BY 'Secret_123';
``` 
```sh
    GRANT ALL PRIVILEGES ON produtos_jdbc.* TO 'Adiministrador'@'localhost';
``` 
Pronto, a partir de agora o código já pode ser utilizado para manutenção desse banco de dados.

