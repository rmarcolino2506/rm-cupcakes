# Registro de testes — RM CupCakes

**Data informada para os testes:** 16/11/2026. Registrar apenas os resultados e participantes que efetivamente realizaram a avaliação desta versão.

| # | Participante | O que testou e funcionou | Problema relatado | Funcionalidade não testada / observação |
|---|---|---|---|---|
| 1 | Nicolas Loguércio Nunes | Filtrou sabores por Todas, Tradicionais, Veganos e Sem glúten. | Não identificava os cupcakes adicionados sem consultar a sacola do menu. | Aplicação de cupom de desconto não implementada. |
| 2 | Alexandre Batista de Morais | Usou o menu de navegação para ir às seções. | O cardápio não apresentou cupcakes. | Histórico de pedidos não foi testado pelo participante. A aplicação dispõe de uma listagem demonstrativa de pedidos. |
| 3 | Maria Helena Ferrari | Adicionou sabores e concluiu o pedido. | A seleção de PIX foi recusada como forma de pagamento inválida. | Cálculo de frete por CEP/região não implementado. |
| 4 | Marcos Pereira dos Santos | Informou endereço, selecionou pagamento e concluiu o pedido. | Nenhuma falha relatada no que foi testado. | Personalização adicional do cupcake não implementada. |
| 5 | Carlos Eduardo Grassano | Adicionou e removeu cupcakes da sacola; não finalizou o pedido. | Nenhuma falha relatada no que foi testado. | Cobrança real por cartão não implementada; os pagamentos são demonstrativos. |

## Laudo de qualidade

A avaliação relatou três problemas: dificuldade para identificar itens na sacola, cardápio vazio e rejeição da opção PIX. Na versão atual, o card do produto mostra a quantidade na sacola, o catálogo lista os cupcakes indisponíveis com essa indicação e o servidor aceita PIX demonstrativo. A confirmação apresenta uma chave fictícia e o total; não ocorre cobrança real.

| Evidência a anexar | Problema relatado | Correção na versão atual | Reteste/evidência |
|---|---|---|---|
| Captura do cardápio vazio e do catálogo atualizado | Produtos não apareciam no cardápio. | Catálogo apresenta produtos e marca os sem estoque como indisponíveis, sem botão de adicionar. | Anexar captura da versão atual. |
| Captura da sacola e do card do produto | Não era fácil saber quais itens estavam na sacola. | Quantidade adicionada aparece no próprio card; a interface é atualizada ao salvar a sacola. | Anexar captura da versão atual. |
| Captura do erro e da confirmação PIX | Servidor recusava PIX. | Back-end aceita PIX; confirmação mostra chave fictícia e total do pedido. | Anexar captura da versão atual; pagamento é apenas simulado. |

Os participantes não relataram falhas nos testes 4 e 5 dentro do escopo que verificaram. No teste 2, o histórico não foi testado pelo participante; a aplicação possui uma listagem demonstrativa de pedidos. Inserir evidências capturadas na versão atualizada antes da entrega.
