# O Inferno Verde

**O Inferno Verde: O Preço da Expedição** é um RPG de mesa sobre exploração, sobrevivência, desgaste e escambo em uma vasta terra tropical fictícia inspirada nas expedições dos séculos XV e XVI.

A expedição deixa os assentamentos costeiros e avança por um interior hostil, onde distância, fome, doença, equipamento danificado, decisões difíceis e fenômenos que ninguém compreende completamente podem cobrar um preço alto.

O projeto reúne as regras do jogo, o cenário, relatos, direção visual, regras de renderização e pipelines usados para produzir o booklet e seus materiais gráficos.

---

## Versões

O projeto é dividido em arquivos versionados. Cada arquivo possui uma responsabilidade específica; juntos, eles definem o jogo e orientam sua produção.

### `Diretivas`

Reúne regras gerais de trabalho com os próprios sources.

Define, entre outras coisas:
- usar sempre a maior versão disponível de cada arquivo;
- criar uma nova versão quando um source for alterado;
- não levar instruções operacionais para o texto do livro;
- evitar abreviações.

### `Regras`

É a referência principal para **como o jogo funciona**.

Contém as regras mecânicas e as listas canônicas usadas pelo jogo, como Ocupações, Pertences, perigos, Provações, Relíquias e outros elementos de sistema.

Quando houver dúvida sobre funcionamento mecânico, quantidade, nome ou efeito de um elemento de jogo, este é o source principal.

### `Cenario`

Define **o mundo de O Inferno Verde** e o que é coerente dentro dele.

Estabelece:
- a referência histórica e tecnológica inspirada nos séculos XV e XVI;
- a natureza da expedição e da exploração do interior;
- a selva, os rios, os assentamentos e os perigos do ambiente;
- povos, conflitos e relações;
- o papel do Desconhecido e os limites daquilo que deve ou não ser explicado.

É a principal referência para coerência histórica, ambiental e narrativa.

### `Relatos`

Reúne fragmentos narrativos, testemunhos, cenas e mini-contos usados para ambientação.

Os relatos ajudam a estabelecer:
- atmosfera;
- linguagem;
- situações de viagem;
- medo, desgaste e tensão;
- manifestações ambíguas do Desconhecido.

Eles podem inspirar VINHETAS, CENAS e outros materiais narrativos. Nem tudo que aparece nos relatos precisa ser interpretado como verdade objetiva do cenário.

### `Images`

Define **como o projeto deve parecer visualmente**.

Reúne a direção de arte das ilustrações, incluindo:
- preto, branco e cinza neutro;
- fundo branco;
- gravura histórica e linha limpa;
- floresta tropical;
- horror, mistério e Desconhecido;
- coerência histórica;
- composição e espaço negativo;
- regras para CARD, FOLHA, VINHETA e CENA;
- integração entre figura, nome e ornamentação editorial;
- proibições como molduras de card, dashboards e elementos visuais incompatíveis.

É o source principal antes de qualquer etapa visual.

### `Render`

Define **como uma imagem aprovada deve ser preparada tecnicamente**.

Cuida de:
- PREVIEW e FINAL RASTER;
- dimensões;
- proporções;
- resolução e PPI;
- PNG e espaço de cor;
- fundo branco;
- upscale controlado;
- montagem determinística de cards e Folhas;
- validação técnica dos arquivos finais.

`Images` define a aparência; `Render` define a entrega técnica.

### `Livro`

Define a apresentação editorial do livro físico, PDF e versão web.

Estabelece:
- tipografia;
- hierarquia de títulos;
- texto corrido;
- referências rápidas;
- uso de Noto Serif;
- uso de EB Garamond;
- espaçamento e integração entre texto e gravuras.

É a referência principal para composição editorial e tipográfica.

### `Pipelines`

Define **como executar os trabalhos do projeto**.

Contém os comandos `RODE: ...` e organiza a sequência de etapas para gerar, revisar, montar, finalizar ou versionar materiais.

Ele não substitui os outros sources. Um pipeline consulta `Regras`, `Cenario`, `Relatos`, `Images`, `Render`, `Livro` e `Diretivas` conforme a tarefa.

### `Itch`

Contém somente regras específicas para materiais destinados ao **itch.io**.

Define limitações próprias desse uso, como formato, tamanho máximo de arquivo e dimensões recomendadas para capa.

Essas regras não devem ser aplicadas automaticamente aos arquivos do livro quando o destino não for itch.io.

### Arquivos de apoio

`README` é o guia de entrada e de uso do projeto.

`LICENSE` registra a licença e o copyright.

Esses dois arquivos acompanham o projeto, mas não substituem os sources que definem conteúdo, direção visual ou produção.

---


### Como funciona o versionamento

Sempre use a maior versão disponível de cada arquivo:

```text
Nome.v1.txt
Nome.v2.txt
Nome.v3.txt
```

Neste exemplo, `Nome.v3.txt` é a versão vigente.

Ao alterar um arquivo versionado, crie uma nova versão em vez de sobrescrever a anterior.

---

## Como usar os pipelines

Os trabalhos do projeto começam com um comando:

```text
RODE: NOME
```

Exemplo:

```text
RODE: RELÍQUIAS
```

O pipeline consulta automaticamente os arquivos aplicáveis, usa sempre suas versões mais recentes e mostra as ações disponíveis para continuar, ajustar ou cancelar.

Quando houver geração de imagem, antes de `ARTE` o pipeline informa também as opções que serão válidas depois da imagem em `DEPOIS DA ARTE:`.

Antes de `ARTE`, o controlador também apresenta um `CONTEXTO DA ETAPA` pesquisado nos sources atuais. Ele separa **Conteúdo Canônico** (o que desenhar) de **Direção Plástica** (como desenhar), resolve aspectos como estilo, densidade, fundo, iluminação, contraste, hachura, composição, espaço negativo, acabamento e peso sinistro, registra a pressão visual e todas as travas aplicáveis da geração e termina com uma síntese visual final que pode ser detalhada; ela não substitui nem reduz os blocos anteriores.

O projeto usa agora três tipos de contexto antes de qualquer transformação visual:

- **CONTEXTO DE GERAÇÃO** — obrigatório antes de criar ou regenerar uma imagem. Usa os cinco blocos completos: Conteúdo Canônico, Direção Plástica, Pressão Visual, Travas e Síntese. Correções também registram a falha, os elementos congelados e exatamente o que pode mudar.
- **CONTEXTO DE ALTERAÇÃO EDITORIAL** — usado antes de aplicar ou ajustar nome, ornamentação, alinhamento, posição ou montagem. É integral: registra todas as fontes consultadas, a fonte visual congelada, objetivo editorial, todos os parâmetros autorizados a mudar, direção editorial completa, relações espaciais, elementos imutáveis, destino real e todos os critérios de validação aplicáveis.
- **CONTEXTO TÉCNICO** — usado antes de FINAL RASTER, upscale, redução, conversão, compressão e exportação. Também é integral: registra fontes consultadas, estado técnico de origem, destino real, especificações completas de destino, transformação permitida e proibida, elementos imutáveis e validação técnica completa.

**Nenhum dos três contextos pode ser reduzido a resumo, brief abreviado, seleção parcial de regras ou referência implícita.** A estrutura muda conforme o tipo de transformação, mas o nível de detalhe deve permanecer completo para tudo que for materialmente aplicável. Só linguagem administrativa de pipeline pode ser excluída quando o contexto for materializado para uma geração visual.

Nenhum desses contextos cria sozinho uma nova etapa de aprovação. Eles preparam e travam a transformação dentro da lógica já existente do pipeline. Uma etapa que altera pixels ou layout não deve começar sem o tipo de contexto correspondente.

O princípio operacional é **uma transformação = um contexto ativo**. Quando um pipeline chama outro para executar a mesma transformação sobre o mesmo alvo, o contexto já preparado é herdado e validado em vez de ser recalculado. A sequência é **HERDAR → VALIDAR → DELTA SE NECESSÁRIO → EXECUTAR**. Em coleções e lotes, decisões realmente comuns formam uma base compartilhada; cada card recebe apenas seu delta individual.

Um novo contexto só é criado quando muda o tipo de transformação, o alvo, a fonte visual, o escopo ou alguma regra material. Isso impede que `VINHETA → RASTER`, `CENA → RASTER` e `FLUXO BASE → CARD` sobrescrevam uma direção visual já resolvida.

### Carregamento do contexto no gerador

Antes de cada chamada de geração, o contexto ativo é convertido em um **PROMPT CONSOLIDADO DA IMAGEM**. Esse prompt não é um resumo nem um novo contexto: é a materialização integral e autossuficiente da base comum + delta individual para exatamente uma saída visual. Ele repete dentro da própria chamada todos os detalhes relevantes de Conteúdo Canônico, Direção Plástica, Pressão Visual, Travas, coerência histórica, regras de unicidade e, quando houver correção, elementos congelados e alteração permitida. A Síntese para a Geração entra apenas no final como reforço e nunca substitui os blocos completos.
Cada chamada ao gerador é **autossuficiente**: não usa atalhos como “mesmo estilo acima”, “conforme contexto anterior” ou “seguir as regras já definidas”. Em lotes, cada imagem repete integralmente a base relevante e acrescenta seu delta individual; assuntos diferentes continuam sendo gerados em chamadas separadas. O contexto não é reduzido para economizar tamanho de prompt.


Antes de `image_gen`, o prompt é validado para confirmar que descreve **um único assunto**, não pede grid, colagem, folha, galeria ou conjunto e não pede nomes, códigos, legendas ou numeração quando a etapa é arte sem texto. O contexto só é considerado efetivamente carregado para a geração depois dessa validação.

Para coleções, Folhas e `RODE: LOTE`, assuntos diferentes são sempre gerados por **chamadas individuais sequenciais**, uma chamada por item, dentro do mesmo MODO ARTE. O lote continua sendo uma unidade operacional para aprovação e progresso, mas não é mais uma única chamada contendo vários assuntos. `n > 1` só serve para variações do mesmo assunto quando isso for explicitamente desejado.

Cada chamada individual carrega semanticamente as travas: **uma única ilustração independente, um único assunto, sem grid, colagem, mosaico, folha, painel, conjunto, texto, nome, código, legenda ou numeração**, além das demais regras aplicáveis de `Images`.

Comandos genéricos como `AJUSTAR`, `REFAZER` e `CORRIGIR` são classificados antes da execução: reinterpretação visual usa CONTEXTO DE GERAÇÃO; composição, crop, posição, nome, ornamento ou montagem usam CONTEXTO DE ALTERAÇÃO EDITORIAL; resolução, PPI, formato, reamostragem, compressão e exportação usam CONTEXTO TÉCNICO. Se um pedido misturar tipos, ele é dividido em transformações sequenciais, cada uma com seu contexto.

Apresentar diretamente um artefato visual existente não cria nova transformação. Se for necessário gerar um arquivo reduzido, comprimido, convertido ou reamostrado apenas para visualização, essa derivação usa CONTEXTO TÉCNICO.

Em `RODE: VINHETA`, o CONTEXTO DE GERAÇÃO é adaptado à **escala editorial**: foco simples, leitura rápida, espaço negativo e densidade controlada para não competir com o texto. Em `RODE: CENA`, ele é adaptado à **página inteira**: hierarquia de planos, profundidade ambiental, distribuição de detalhe, iluminação da situação e sinais secundários de mistério. Em ambos, peso sinistro vem do conteúdo e da consequência, não de escurecer a arte. Se VINHETA ou CENA receber ornamentação posterior, a ornamentação é tratada como transformação separada, com CONTEXTO DE ALTERAÇÃO EDITORIAL e, se houver fragmento gerado, CONTEXTO DE GERAÇÃO especializado seguido de revalidação editorial antes da aplicação.

### Criação de imagens

- `RODE: VINHETA` — cria uma única ilustração editorial integrada ao fluxo do texto.
- `RODE: CENA` — cria uma única ilustração narrativa concebida para página inteira.
- `RODE: CARD` — cria a ilustração individual destinada a uma posição de uma Folha.
- `RODE: FOLHA` — produz uma Folha completa com até 8 cards em 4 colunas por 2 linhas.
- `RODE: COLEÇÃO` — distribui uma lista com mais de 8 elementos em várias Folhas.
- `RODE: LOTE` — produz de 2 a 10 imagens independentes no mesmo lote operacional; assuntos diferentes usam uma chamada individual por imagem, sem montar grid ou Folha.

### Coleções do jogo

- `RODE: OCUPAÇÕES` — produz cards e Folhas usando as Ocupações canônicas de `Regras`.
- `RODE: CRIATURAS` — produz cards e Folhas com Criaturas e Ameaças canônicas.
- `RODE: RELÍQUIAS` — produz cards e Folhas com as Relíquias canônicas.
- `RODE: PERIGOS` — produz cards e Folhas com Perigos Estranhos ou ligados ao Desconhecido.
- `RODE: NATURAIS` — produz cards e Folhas com Perigos Naturais e Ambientais da jornada.
- `RODE: ARMAS` — produz cards e Folhas com as Armas canônicas.
- `RODE: PROTEÇÕES` — produz cards e Folhas com Proteções e Vestimentas canônicas.
- `RODE: SUPRIMENTOS` — produz cards e Folhas com ferramentas, utilitários, munição e consumíveis.
- `RODE: PROVAÇÕES` — produz cards e Folhas com Provações comuns e do Desconhecido.
- `RODE: RUMORES` — produz cards e Folhas com Rumores e Sinais do Impossível.
- `RODE: LOCAIS` — produz cards e Folhas com Postos e Locais de Expedição definidos nas fontes.
- `RODE: RELATOS` — produz cards e Folhas baseados nos relatos canônicos do projeto.

### Produção e manutenção

- `RODE: RASTER` — conduz uma imagem da PREVIEW validada até o raster mestre final.
- `RODE: CORRIGIR` — refaz somente um card que falhou, preservando os demais já aprovados.
- `RODE: MONTAR` — monta deterministicamente uma Folha a partir dos cards completos aprovados.
- `RODE: FINAL` — prepara tecnicamente uma PREVIEW já aprovada para produção.
- `RODE: DIGITAL` — cria uma versão reduzida ou derivada a partir de um FINAL RASTER aprovado.
- `RODE: VERSÃO` — cria uma nova versão de um arquivo sem sobrescrever a versão anterior.

Para interromper qualquer pipeline ativo, use:

```text
CANCELAR
```

---


## Cards e Folhas

Nos cards, a ilustração e a composição editorial são tratadas separadamente para permitir revisão antes da montagem da Folha.

- **PREVIEW DA ARTE** — mostra somente a ilustração narrativa, ainda sem nome ou ornamentos editoriais.
- **APROVAÇÃO DA ARTE** — fixa a ilustração que será preservada nas etapas seguintes.
- **FINAL RASTER DA FIGURA** — prepara tecnicamente a figura aprovada no tamanho mestre do card, sempre sob CONTEXTO TÉCNICO.
- **NOME** — aplica o nome canônico em Noto Serif SemiBold, próximo da figura e sem caixas ou placas, sob CONTEXTO DE ALTERAÇÃO EDITORIAL.
- **ORNAMENTOS EDITORIAIS** — depois de figura + nome, só adiciona ornamento quando ele tiver âncora em `Cenario`, `Regras` ou `Relatos` e também responder ao ritmo visual real do card; a alteração usa CONTEXTO DE ALTERAÇÃO EDITORIAL e, se o fragmento precisar ser gerado, também um CONTEXTO DE GERAÇÃO especializado baseado no próprio CARD FIGURA + NOME. Depois que o fragmento real for aprovado, o contexto editorial é revalidado para posição, escala, peso de linha e integração antes da aplicação determinística. Se parecer um elemento colado ou não fizer falta quando removido, o card fica sem ornamento.
- **PREVIEW DO CARD COMPLETO** — mostra figura, nome e ornamentação na composição final do card.
- **APROVAÇÃO DO CARD COMPLETO** — fixa o card completo antes de ele entrar na Folha.
- **MONTAGEM DA FOLHA** — posiciona deterministicamente até 8 cards completos no grid de 4 colunas por 2 linhas, sob CONTEXTO DE ALTERAÇÃO EDITORIAL; `AJUSTAR MONTAGEM` atualiza esse contexto antes de qualquer reposicionamento.
- **APROVAÇÃO DA FOLHA** — permite revisar o conjunto, o ritmo visual, as posições e os espaços vazios.
- **FINAL RASTER DA FOLHA** — exporta a Folha aprovada no tamanho, formato e resolução definidos por `Render`, sob CONTEXTO TÉCNICO.

Os nomes usam **Noto Serif SemiBold**.

Os títulos editoriais usam **EB Garamond**.

A direção visual, coerência histórica, horror, mistério, floresta e regras técnicas são aplicadas automaticamente pelos arquivos do projeto durante os pipelines.

---


## Contribuições

Contribuições são bem-vindas.

Correções, sugestões de regras, relatos, material de cenário, melhorias de acessibilidade, testes de jogo, arte e ajustes nos pipelines podem ajudar o projeto a crescer.

Ao contribuir:

- preserve o tom e a proposta de **O Inferno Verde**;
- respeite a coerência do cenário e sua referência histórica;
- evite substituir conteúdo canônico sem indicar claramente a mudança;
- mantenha o sistema de versionamento dos sources;
- descreva de forma clara o que foi alterado e por quê.

Contribuições incorporadas ao projeto são publicadas sob a mesma licença do projeto, salvo acordo explícito em contrário.

---

## Licença

**O Inferno Verde** é disponibilizado sob a licença **Creative Commons Atribuição–NãoComercial–CompartilhaIgual 4.0 Internacional — CC BY-NC-SA 4.0**.

Em resumo, a licença permite compartilhar e adaptar o material, desde que:

- seja dado o devido crédito;
- o uso não seja comercial;
- trabalhos derivados sejam distribuídos sob a mesma licença.

Consulte `LICENSE.v1.txt` para a identificação da licença e o endereço oficial do texto legal.

---

**Copyright © 2026 Fellipe Ugliara.**

**O Inferno Verde: O Preço da Expedição** — alguns direitos reservados sob CC BY-NC-SA 4.0.

