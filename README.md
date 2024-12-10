# Refinando um Projeto Conceitual de Banco de Dados – E-COMMERCE

## Introdução

Este projeto foi desenvolvido como parte do desafio proposto no curso **"Refinando um Projeto Conceitual de Banco de Dados – E-COMMERCE"** do bootcamp **"Suzano - Análise de Dados com Power BI"**, disponível na plataforma **web.dio.me**.

Durante o curso, conduzido pela professora **Juliana Mascarenhas**, fomos introduzidos à criação de um esquema conceitual de banco de dados utilizando o **MySQL Workbench**. O ponto de partida do projeto incluía as entidades principais **Cliente**, **Produto** e **Pedido**, juntamente com um enredo que explorava as interações entre essas entidades.

A partir dessa base, fui desafiado a refinar e expandir o modelo inicial, aplicando melhorias e incorporando novas técnicas de modelagem de dados.

---

## Desenvolvimento

No decorrer do desenvolvimento, foram realizadas diversas melhorias no esquema inicial, com a aplicação de técnicas avançadas de modelagem, tais como **generalização**, **especialização** e refinamento de entidades e relacionamentos. As principais mudanças incluem:

### 1. Cliente (Generalização e Especialização)
- Divisão da entidade **Cliente** em duas subclasses:
  - **Pessoa Física (PF)**: Inclui informações específicas, como CPF e data de nascimento.
  - **Pessoa Jurídica (PJ)**: Abrange CNPJ, razão social e nome fantasia.
- Garantia de que cada cliente pode ser **PJ ou PF**, mas nunca ambos, respeitando o conceito de exclusividade.

### 2. Forma de Pagamento (Generalização e Detalhamento)
- Criação da entidade **Forma de Pagamento**, com especialização para:
  - **Cartão de Crédito**: Inclui dados específicos, como número do cartão, titular, bandeira e CVV.
  - **PIX**: Armazena a chave PIX (CPF, e-mail, telefone, etc.).
  - **Boleto Bancário**: Contém código de barras e status do pagamento.
  - **Transferência Bancária**: Inclui banco, agência e conta.

### 3. Entrega
- Adição da entidade **Entrega**, vinculada ao **Pedido**, com os campos:
  - **Status da Entrega**: Pendente, em trânsito, entregue ou cancelado.
  - **Código de Rastreamento**: Para monitorar o transporte dos produtos.

### 4. Endereço
- Criação da entidade **Endereço** para armazenar informações relacionadas a:
  - Logradouro, número, complemento, bairro, cidade, estado e CEP.
- Esta entidade foi idealizada com base no conceito de **especialização**, pois representa diferentes tipos de endereços que podem ser associados a:
  - **Clientes** (endereço residencial ou comercial).
  - **Pedidos** (endereço de entrega ou cobrança).

### 5. Refinamento Geral
- Inclusão de novas validações e restrições para melhorar a consistência dos dados.
- Adaptação às boas práticas de modelagem relacional para garantir escalabilidade e integridade.

---