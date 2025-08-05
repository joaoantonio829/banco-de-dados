# banco-de-dados
---
## Conceitos Rápidos

### Banco de Dados Relacional
Ele Utiliza tabelas que se relacionam entre si. É ideal para dados bem estruturados e que seguem regras rígidas.  
**Exemplo**: sistemas de escolas, lojas, hospitais.
<img width="1326" height="598" alt="image" src="https://github.com/user-attachments/assets/03298f13-e927-4c39-92cd-edde7ab8b5b9" />

### Banco de Dados Não Relacional
Mais flexível, armazena dados em formatos como JSON, sem necessidade de estrutura fixa.  
**Exemplo**: MongoDB, muito usado em aplicativos modernos e projetos com dados variáveis.
<img width="765" height="430" alt="image" src="https://github.com/user-attachments/assets/11691ecb-063d-4ca2-8cfa-f321f5ecef9e" />

### Normalização
É o processo de organizar os dados para evitar redundância e facilitar a manutenção.  
Melhora a eficiência, reduz inconsistências e facilita atualizações.
<img width="726" height="259" alt="image" src="https://github.com/user-attachments/assets/3f43a51f-99bf-4bfd-9006-edfbc5307789" />

---

## Tabela Não Normalizada

| Pedido_ID | Nome        | Endereço     | Produto_ID | Produto | Qtd | Preço_Total |
|-----------|-------------|--------------|------------|---------|-----|--------------|
| 1         | João Silva  | Rua A, 123   | 10         | Caneta  | 2   | 4.00         |
| 1         | João Silva  | Rua A, 123   | 11         | Lápis   | 1   | 2.00         |
| 2         | Maria Souza | Av. B, 456   | 10         | Caneta  | 5   | 10.00        |

---

## Tabelas Normalizadas

### Clientes

| Cliente_ID | Nome        | Endereço     |
|------------|-------------|--------------|
| 1          | João Silva  | Rua A, 123   |
| 2          | Maria Souza | Av. B, 456   |

### Produtos

| Produto_ID | Nome   |
|------------|--------|
| 10         | Caneta |
| 11         | Lápis  |

### Pedidos

| Pedido_ID | Cliente_ID |
|-----------|------------|
| 1         | 1          |
| 2         | 2          |

### Itens_Pedido

| Pedido_ID | Produto_ID | Quantidade | Preço_Total |
|-----------|------------|------------|-------------|
| 1         | 10         | 2          | 4.00        |
| 1         | 11         | 1          | 2.00        |
| 2         | 10         | 5          | 10.00       |

---

## Modelo Não Relacional (MongoDB)

```json
{
  "pedido_id": 1,
  "cliente": {
    "nome": "João Silva",
    "endereco": "Rua A, 123"
  },
  "itens": [
    {
      "produto_id": 10,
      "nome": "Caneta",
      "quantidade": 2,
      "preco_total": 4.00
    },
    {
      "produto_id": 11,
      "nome": "Lápis",
      "quantidade": 1,
      "preco_total": 2.00
    }
  ]
}
