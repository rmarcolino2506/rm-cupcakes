# Projeto Integrador Transdisciplinar II — RM CupCakes

## Identificação
- **Estudante:** Ricardo Henrique de Melo Marcolino
- **RGM:** 36052353
- **Projeto:** aplicação web demonstrativa para venda de cupcakes gourmet
- **Continuidade do PIT I:** Situação-problema 2 — modelagem UML de um sistema de vendas de cupcakes

## Objetivo
Implementar um protótipo web simples que demonstre os principais fluxos representados nos artefatos UML do PIT I: consultar produtos, montar uma sacola, revisar um pedido, selecionar uma forma de pagamento demonstrativa e registrar o pedido.

## Relação com o PIT I e revisão conceitual
O PIT I propôs representar um aplicativo de vendas de cupcakes por meio de casos de uso, casos de uso expandidos, diagrama de classes e diagrama de sequência. Neste PIT II, a aplicação web transforma em protótipo parte desses fluxos. A modelagem orientada a objetos e a UML ajudam a descrever atores, responsabilidades, entidades e mensagens entre interface, servidor e banco de dados. A solução é uma aplicação web responsiva, não um aplicativo nativo instalado em celular.

## Escopo implementado
| Funcionalidade | Situação no MVP |
|---|---|
| Consultar catálogo, buscar e filtrar cupcakes | Implementada |
| Adicionar, ajustar e remover itens da sacola | Implementada |
| Informar endereço e revisar o pedido | Implementada |
| Selecionar PIX, cartão ou pagamento na entrega | Demonstrativa; não cobra |
| Registrar pedido, calcular total e atualizar estoque | Implementada no servidor e SQLite |
| Consultar pedidos registrados | Implementada para demonstração |
| Cadastro/login, entrega real e pagamento real | Não implementados |

## Diagramas UML
Os diagramas de casos de uso, classes e sequência do fluxo de registro de pedido estão em [DIAGRAMAS_UML.md](DIAGRAMAS_UML.md). As especificações textuais dos casos de uso expandidos estão em [CASOS_DE_USO_EXPANDIDOS.md](CASOS_DE_USO_EXPANDIDOS.md). Os artefatos foram limitados às funções presentes no protótipo para manter a documentação coerente com a implementação.

## Tecnologias e execução
| Campo | Informação |
|---|---|
| Front-end | HTML, CSS e JavaScript; fonte Sora |
| Back-end | JavaScript com Node.js 26 |
| Banco de dados | SQLite local (`rm-cupcakes.sqlite`) |
| Hospedagem | A definir após publicação da versão do Ricardo |
| Plataforma | Aplicação web acessada pelo navegador |
| Modo de codificação | Tradicional |
| Repositório GitHub | A preencher |
| Link da aplicação | A preencher após publicação |
| Vídeos | A gravar |

Para executar localmente, abra o terminal nesta pasta e rode `node server.js`; depois acesse `http://localhost:3000`. O servidor cria e inicializa o banco local automaticamente.

## Qualidade e limitações
O checkout, PIX, cartão e entrega são demonstrativos. Não há cobrança, integração bancária, autenticação de clientes nem processamento de entrega. Os testes e o laudo de qualidade devem registrar resultados observados e evidências reais, sem inventar participantes ou ocorrências. A hospedagem pública e persistência de dados serão confirmadas após configurar o serviço do Ricardo.
