# Exercício 1
Agora que sabemos como implementar relações do tipo 1:m e 1:1, vamos refatorar a estrutura do Labecommerce!<br>
Por ora não precisaremos editar as tabelas já existentes (users e products). Nosso objetivo hoje é criar a tabela de pedidos (purchases).

## Criação da tabela de **pedidos**
- nome da tabela: **purchases**
- colunas da tabela:
  - id (TEXT, PK, único e obrigatório)
  - total_price (REAL, único e obrigatório)
  - paid (INTEGER e obrigatório)
  - deliveredAt (TEXT e opcional)
  - buyer_id (TEXT, obrigatório e FK = referencia a coluna id da tabela users)

### Observações
A coluna paid será utilizada para guardar uma lógica booleana. O SQLite recomenda o uso do número 0 para false e 1 para true.<br>
Os pedidos começam com paid valendo 0 e quando o pagamento for finalizado, se atualiza para true.<br>
<br>
A coluna deliveredAt será utilizada para gerenciar a data de entrega do pedido. Ela é opcional, porque sempre começará sem valor ao criar um pedido, ou seja, null.<br>
O SQLite recomenda utilizar TEXT para lidar com strings no formato ISO8601 "aaaa/mm/dd hh:mm:sss". Lembre-se da existência da função nativa DATETIME.<br>