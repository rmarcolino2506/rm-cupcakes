# Casos de Uso Expandidos — RM CupCakes

Especificações textuais dos casos de uso centrais do protótipo. O sistema é uma aplicação web demonstrativa; pagamento e entrega não são processados de verdade.

## UC01 — Consultar catálogo

- **Ator principal:** Cliente
- **Objetivo:** localizar cupcakes e verificar disponibilidade e preço.
- **Pré-condição:** aplicação acessível e catálogo carregado.
- **Fluxo principal:**
  1. O cliente abre a seção do cardápio.
  2. O sistema apresenta os produtos, categorias, preços e disponibilidade.
  3. O cliente pode pesquisar por nome ou ingrediente e selecionar uma categoria.
  4. O sistema atualiza os resultados conforme a pesquisa e o filtro.
- **Fluxo alternativo:** se a pesquisa não encontrar produtos, o sistema apresenta uma mensagem de resultado vazio. Produto sem estoque aparece como indisponível e não pode ser adicionado.
- **Pós-condição:** o cliente visualiza os produtos correspondentes à pesquisa/filtro, sem alteração nos dados.

## UC02 — Gerenciar sacola

- **Ator principal:** Cliente
- **Objetivo:** selecionar produtos e quantidades antes de enviar um pedido.
- **Pré-condição:** catálogo carregado; para incluir um produto, ele deve ter estoque disponível.
- **Fluxo principal:**
  1. O cliente seleciona adicionar em um produto disponível.
  2. O sistema atualiza a quantidade no card e na sacola.
  3. O cliente abre a sacola e pode aumentar ou diminuir quantidades.
  4. O sistema recalcula subtotais e total.
- **Fluxos alternativos:** se o estoque máximo for atingido, o sistema avisa e não aumenta a quantidade. Se a quantidade for reduzida a zero, o item é removido.
- **Pós-condição:** a sacola contém os itens e quantidades escolhidos; o conteúdo permanece no navegador até ser alterado ou o pedido ser confirmado.

## UC03 — Revisar e registrar pedido

- **Ator principal:** Cliente
- **Objetivo:** enviar um pedido demonstrativo com endereço e forma de pagamento selecionada.
- **Pré-condições:** sacola com pelo menos um produto; endereço preenchido; forma de pagamento selecionada.
- **Fluxo principal:**
  1. O cliente informa o endereço e escolhe uma forma de pagamento.
  2. O sistema apresenta itens, endereço, pagamento escolhido e total para revisão.
  3. O cliente confirma o pedido.
  4. O navegador envia os dados à API.
  5. O servidor valida endereço, pagamento, produtos e estoque disponível.
  6. O servidor grava o pedido e seus itens e reduz o estoque em uma transação SQLite.
  7. O sistema apresenta o identificador, status e total do pedido.
- **Fluxos alternativos:** endereço inválido, forma de pagamento não aceita, produto inexistente ou estoque insuficiente resultam em mensagem de erro e o pedido não é gravado. Se a solicitação falhar, o cliente pode corrigir os dados e tentar novamente.
- **Pós-condição de sucesso:** pedido registrado com status “Recebido”, itens e total; estoque atualizado. O pagamento permanece não processado.

## UC04 — Consultar pedidos registrados

- **Ator principal:** Responsável pela loja
- **Objetivo:** visualizar os pedidos gravados para a demonstração.
- **Pré-condição:** aplicação acessível; pedidos podem não existir ainda.
- **Fluxo principal:**
  1. O ator abre a seção de pedidos.
  2. O sistema consulta a API de pedidos.
  3. O sistema apresenta identificador, data, status, itens, endereço, pagamento escolhido e total.
- **Fluxo alternativo:** se ainda não houver pedidos, o sistema informa que a lista está vazia. Se a API falhar, apresenta uma mensagem de erro.
- **Pós-condição:** os pedidos são exibidos sem alteração dos registros.
- **Observação de escopo:** a demonstração não implementa autenticação; a seção não deve ser tratada como painel administrativo seguro.
