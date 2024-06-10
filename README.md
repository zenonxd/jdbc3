Para realizar a inserção de dados utilizamos o preparedStatement, encapsulado dentro de um bloco try.
![image](https://github.com/zenonxd/jdbc3/assets/64092861/97db37a1-9640-43af-bbd1-ef2a32c170d0)

Não esquecer de instanciar a connection (conn) e o st.

O (?) é um placeholder, depois iremos colocar os dados a serem inseridos. Uma ? para cada valor.


Para inserimos os dados usamos st.String por exemplo (caso seja uma string).
![image](https://github.com/zenonxd/jdbc3/assets/64092861/5e4aafb7-17d5-40bb-9e7b-8844c2ee5534)
O numero 1 é a primeira interrogação e assim sucessivamente.

Para inserir datas é um pouco diferente. Precisamos criar um SimpleDateFormat e passar a classe java.sql.Date.
![image](https://github.com/zenonxd/jdbc3/assets/64092861/bafd9ded-453b-4256-aa70-7f26ee44dee6)

Após inserirmos os dados, usamos: ![image](https://github.com/zenonxd/jdbc3/assets/64092861/5e4723b7-112c-42f3-a959-f76c9b5d43ee)

O executeUpdate retorna um numero inteiro (a quantidade de rows que foram afetadas).
Por isso o correto é atribuir esse comando a uma variável do tipo int: ![image](https://github.com/zenonxd/jdbc3/assets/64092861/22baa123-4ae8-4196-80b6-f16be01820fa)

//
Após inserir esses dados, como retornar a ID inserida? Após passarmos os parametros a serem inseridos e as (?, ?, ?) colocamos uma vírgula e passamos uma sobrecarga:

![image](https://github.com/zenonxd/jdbc3/assets/64092861/89077626-fe29-4c4b-8e9c-212f9ba061b2)

Para tratarmos as rows afetadas pelo update, utilizaremos um if.

![image](https://github.com/zenonxd/jdbc3/assets/64092861/0ff333a9-68d2-4692-bbd8-1ab6f5d5056c)

getGenerateKeys() retorna o codigo inserido. Esse código é um objeto do tipo ResultSet.
Para fazermos a leitura desse objeto do tipo ResultSet, utilizamos um while.

![image](https://github.com/zenonxd/jdbc3/assets/64092861/20f0e699-e8ac-4412-bbf9-8b173b003767)

Esse 1 indica que queremos a primeira coluna.

