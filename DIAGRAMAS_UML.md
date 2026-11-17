# Diagramas UML — RM CupCakes

Diagramas de análise para a aplicação web demonstrativa. Os fluxos representam somente as funcionalidades presentes no MVP.

## 1. Casos de uso

```mermaid
flowchart LR
  cliente[Cliente]
  operador[Responsável pela loja]
  subgraph sistema[RM CupCakes — aplicação web]
    catalogo((Consultar catálogo))
    busca((Buscar e filtrar cupcakes))
    sacola((Gerenciar sacola))
    pedido((Revisar e registrar pedido))
    pagamento((Selecionar pagamento demonstrativo))
    pedidos((Consultar pedidos registrados))
  end
  cliente --- catalogo
  cliente --- busca
  cliente --- sacola
  cliente --- pedido
  pedido --- pagamento
  operador --- pedidos
```

## 2. Diagrama de classes

```mermaid
classDiagram
  class Produto {
    +int id
    +string nome
    +string descricao
    +decimal preco
    +string categoria
    +int estoque
  }
  class Pedido {
    +string id
    +datetime criadoEm
    +string status
    +string endereco
    +string formaPagamento
    +decimal total
  }
  class ItemPedido {
    +int quantidade
    +decimal precoUnitario
    +decimal subtotal
  }
  Pedido "1" *-- "1..*" ItemPedido : contém
  ItemPedido "*" --> "1" Produto : referencia
```

## 3. Diagrama de sequência — registrar pedido

```mermaid
sequenceDiagram
  actor Cliente
  participant Navegador
  participant Servidor as Node.js/API
  participant Banco as SQLite
  Cliente->>Navegador: Escolhe cupcakes e informa endereço/pagamento
  Navegador->>Servidor: POST /api/orders (itens, endereço, pagamento)
  Servidor->>Banco: Consulta produtos e estoque
  Banco-->>Servidor: Produtos, preços e quantidades disponíveis
  Servidor->>Servidor: Valida pedido e calcula total
  Servidor->>Banco: Grava pedido/itens e reduz estoque (transação)
  Banco-->>Servidor: Confirma gravação
  Servidor-->>Navegador: Pedido registrado, status e total
  Navegador-->>Cliente: Exibe confirmação demonstrativa
```

Os diagramas foram escritos em Mermaid para facilitar a revisão no GitHub. Eles podem ser exportados para imagem pelo diagrams.net ou por um renderizador Mermaid se o relatório exigir arquivos de imagem.
