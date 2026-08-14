# O Inferno Verde — Guia de Uso

**Versão 12**

Este README é um **guia rápido para usar o projeto**.

Você não precisa decorar os arquivos internos nem repetir as regras visuais, de cenário ou de renderização. Use os comandos `RODE:` e o pipeline consulta os sources aplicáveis.

Durante o uso, **status e opções aparecem somente como texto da conversa**. O projeto nunca deve criar uma imagem de dashboard, painel de execução ou botões desenhados. Quando uma etapa gerar imagem, você verá apenas a própria arte que está sendo produzida.

---

## 1. Como iniciar um trabalho

Digite:

```text
RODE: NOME
```

Exemplo:

```text
RODE: RELÍQUIAS
```

O pipeline inicia, mostra o progresso e conduz o trabalho até o resultado final.

---

## 2. Comandos principais

### Imagens individuais

| Comando | Use para |
|---|---|
| `RODE: VINHETA` | criar uma vinheta editorial |
| `RODE: CENA` | criar uma cena de página inteira |
| `RODE: CARD` | criar um card individual |
| `RODE: RASTER` | gerar uma PREVIEW e depois o FINAL RASTER |
| `RODE: FINAL` | gerar o FINAL RASTER de uma PREVIEW já aprovada |
| `RODE: DIGITAL` | criar uma versão digital derivada do raster mestre |

### Folhas e coleções

| Comando | Use para |
|---|---|
| `RODE: FOLHA` | criar uma Folha a partir de cards |
| `RODE: COLEÇÃO` | criar uma coleção de várias Folhas |
| `RODE: LOTE` | gerar até 10 imagens independentes no mesmo lote |
| `RODE: MONTAR` | montar uma Folha usando cards já aprovados |
| `RODE: CORRIGIR` | corrigir somente a imagem/card necessário |

### Coleções prontas

| Comando | Conteúdo |
|---|---|
| `RODE: OCUPAÇÕES` | Ocupações |
| `RODE: CRIATURAS` | Criaturas e ameaças |
| `RODE: RELÍQUIAS` | Relíquias |
| `RODE: PERIGOS` | Perigos Estranhos e do Desconhecido |
| `RODE: NATURAIS` | Perigos naturais e ambientais |
| `RODE: ARMAS` | Armas |
| `RODE: PROTEÇÕES` | Proteções e vestimentas |
| `RODE: SUPRIMENTOS` | Munição, consumíveis, ferramentas e utilitários |
| `RODE: PROVAÇÕES` | Provações |
| `RODE: RUMORES` | Rumores e Sinais do Impossível |
| `RODE: LOCAIS` | Postos e locais |
| `RODE: RELATOS` | Relatos de exploração |

### Arquivos do projeto

| Comando | Use para |
|---|---|
| `RODE: VERSÃO` | criar uma nova versão de um source alterado |

---

## 3. O que acontece quando um pipeline começa

Durante um pipeline, o status aparece sempre na conversa.

Exemplo:

```text
PIPELINE: RELÍQUIAS — ATIVO
FOLHA: 01/03
PROGRESSO: 0/20 PREVIEWS válidas

✓ 1. Mapa canônico e distribuição — concluído
▶ 2. Gerar PREVIEWS da Folha 01 — ETAPA ATUAL
○ 3. Aprovar/revisar PREVIEWS da Folha 01
○ 4. Gerar FINAL RASTER dos cards da Folha 01
○ 5. Aplicar nomes e montar Folha 01
○ 6. Aprovar Folha 01
○ 7. Gerar FINAL RASTER da Folha 01
○ 8. Gerar PREVIEWS da Folha 02
○ 9. Aprovar/revisar PREVIEWS da Folha 02
○ 10. Gerar FINAL RASTER dos cards da Folha 02
○ 11. Aplicar nomes e montar Folha 02
○ 12. Aprovar Folha 02
○ 13. Gerar FINAL RASTER da Folha 02
○ 14. Gerar PREVIEWS da Folha 03
○ 15. Aprovar/revisar PREVIEWS da Folha 03
○ 16. Gerar FINAL RASTER dos cards da Folha 03
○ 17. Aplicar nomes e montar Folha 03
○ 18. Aprovar Folha 03
○ 19. Gerar FINAL RASTER da Folha 03
○ 20. Encerrar coleção

AÇÕES: GERAR PREVIEWS · AJUSTAR · CANCELAR
```

Enquanto o pipeline estiver ativo, **todas as etapas restantes devem aparecer integralmente**. Não usar atalhos como “repetir para as próximas Folhas”.

---


## Horror, mistério e floresta — o que você precisa fazer

Nada extra.

Ao usar pipelines como:

```text
RODE: RELÍQUIAS
RODE: CRIATURAS
RODE: PERIGOS
RODE: RUMORES
RODE: PROVAÇÕES
RODE: RELATOS
```

o pipeline consulta `Images` automaticamente e prepara antes da arte:

- o foco principal;
- a pressão visual da floresta;
- o sinal inquietante do Desconhecido;
- a pergunta visual que deve permanecer sem resposta;
- o grau de revelação;
- o que não deve aparecer.

A regra prática é:

```text
FOCO + PRESSÃO DA SELVA + SINAL DO DESCONHECIDO
```

O horror deve aparecer principalmente por **vestígio, consequência, ausência, reflexo, rastro, ocultação, comportamento estranho do ambiente ou dúvida**.

O pipeline evita usar como solução padrão:

- aura;
- energia mágica;
- portal;
- runas brilhantes;
- fantasma totalmente revelado;
- entidade explicando a cena.

Antes de mostrar uma PREVIEW, o pipeline verifica quatro pontos:

```text
FLORESTA
HORROR
MISTÉRIO
DESCONHECIDO
```

Quando dois ou mais desses pontos falham, a imagem deve ser refeita antes de ser apresentada para aprovação.

Você não precisa escrever “use Images”, “adicione floresta” ou “deixe mais misterioso” a cada lote. Essas verificações fazem parte do pipeline.

---

## 4. Como funciona CONTROLADOR → ARTE → CONTROLADOR

Para evitar que o gerador desenhe o próprio pipeline, o uso acontece em dois modos.

### CONTROLADOR

Aqui você vê:

- etapa atual;
- todas as etapas que ainda faltam;
- progresso;
- o que será gerado;
- opções curtas de resposta.

Quando a próxima ação for gerar imagens, aparecerá algo como:

```text
AÇÕES: ARTE · AJUSTAR · CANCELAR

DEPOIS DA ARTE: APROVAR TODAS · REVISAR · REFAZER · CANCELAR
```

### ARTE

Digite:

```text
ARTE
```

Nesse turno aparecem **somente as imagens**. O pipeline não mostra status, etapas ou opções junto da geração. Isso é intencional: impede que essas informações sejam interpretadas como parte da imagem.

Depois de ver as imagens, use uma das opções que já foram mostradas antes da geração, por exemplo:

```text
APROVAR TODAS
REVISAR
REFAZER
CANCELAR
```

Sua resposta retorna automaticamente ao modo CONTROLADOR, que atualiza o progresso e mostra todas as etapas restantes.

### Regra prática

```text
RODE: RELÍQUIAS
        ↓
CONTROLADOR
        ↓
ARTE
        ↓
imagens somente
        ↓
APROVAR / REFAZER / REVISAR / CANCELAR
        ↓
CONTROLADOR
```

O turno de ARTE é a única exceção à regra de mostrar o bloco de progresso em toda resposta. As opções pós-geração são mostradas imediatamente antes de entrar em ARTE e continuam válidas depois que as imagens aparecem.

---

## 5. Como aprovar ou pedir mudanças

Quando o pipeline precisar de uma decisão sua, ele termina a mensagem com uma linha `AÇÕES:`.

Exemplo:

```text
AÇÕES: APROVAR TODAS · REVISAR · REFAZER · CANCELAR
```

Para continuar, digite somente uma das palavras ou expressões curtas mostradas. Você não precisa escrever frases completas.

Exemplos comuns:

```text
APROVAR
APROVAR TODAS
REVISAR
REFAZER
AJUSTAR
CORRIGIR CARD
CANCELAR
```

`CANCELAR` deve estar disponível em toda pausa enquanto o pipeline estiver ativo.

Se apenas um card estiver errado, peça para corrigir esse card. Cards já aprovados devem ser preservados.

---

## 6. O que você NÃO precisa lembrar durante o pipeline

Você não precisa escrever instruções como:

```text
use Images
use a fonte correta
adicione ornamentos
aproxime o nome da imagem
```

O pipeline deve fazer isso automaticamente. Antes de gerar ou montar qualquer arte ele consulta a versão mais recente de `Images`.

Na etapa de nomes:
- a fonte obrigatória é **Source Serif 4 Semibold**;
- não existe fallback silencioso;
- se a fonte estiver indisponível, o pipeline para e avisa;
- o nome é colocado próximo da ilustração, não fixado arbitrariamente no rodapé.

Nas Folhas, a ornamentação também é planejada antes da geração. Alguns cards ficam sem ornamento e outros recebem fragmentos esparsos.

Você não precisa escolher manualmente os ornamentos. O pipeline usa as famílias canônicas de `Images`, como:
- Selva Devoradora;
- Expedição e Cartografia;
- Fé, Penitência e Morte;
- Ruína, Ferro e Relicário;
- Água, Lama e Travessia;
- Desconhecido Incompleto.

Os ornamentos devem parecer parte do mundo ou da linguagem editorial do livro, nunca arabescos genéricos de fantasia. A montagem final preserva exatamente a ornamentação aprovada.

---

## 7. PREVIEW e FINAL RASTER

O fluxo normal de uma imagem é:

```text
PREVIEW → APROVAÇÃO → FINAL RASTER
```

### PREVIEW

Use para avaliar visualmente:

- composição;
- personagem ou objeto;
- atmosfera;
- conteúdo;
- anatomia;
- coerência visual.

A PREVIEW **não é o arquivo final**.

### FINAL RASTER

Depois que você aprovar a PREVIEW, o pipeline prepara a versão raster mestre em alta resolução.

Você não precisa pedir novamente “faça em alta resolução” depois de aprovar. Isso já faz parte do pipeline.

Se a criação do raster exigir uma nova geração capaz de mudar a arte, a nova imagem volta a ser PREVIEW e precisa ser aprovada.

---

## 8. O que conta como PREVIEW válida

A PREVIEW deve ser **a própria imagem que está sendo produzida**.

Não são PREVIEWS válidas:

- dashboards;
- infográficos;
- mockups de pipeline;
- folhas de contato;
- imagens mostrando miniaturas do trabalho;
- cards desenhados dentro de uma interface fictícia.

Se você pediu oito cards, as PREVIEWS devem ser **oito imagens reais e independentes**, não uma imagem contendo oito miniaturas.

### Status nunca vira imagem

Durante uma geração de arte, o pipeline separa o controle da criação visual:

```text
arte → geração
status + AÇÕES → conversa
```

A instrução enviada ao gerador contém apenas a descrição da arte. Palavras de controle como pipeline, etapa, progresso, aprovação, cancelar ou dashboard não fazem parte da instrução visual.

---

## 9. O pipeline nunca gera dashboards

Durante o uso, o andamento do pipeline aparece **somente como texto na conversa**.

O gerador de imagens é usado apenas para criar a própria arte solicitada. Ele nunca deve criar:

- dashboard;
- painel de progresso;
- infográfico;
- mockup;
- botões desenhados;
- tela de confirmação;
- folha de contato;
- imagem com miniaturas para mostrar o andamento.

Se isso acontecer, a saída é inválida e não avança o pipeline.

Quando você pedir várias PREVIEWS, espere receber as próprias artes, não uma imagem explicando o pipeline.

---

## 10. Lotes de imagens

Quando houver várias imagens independentes, o pipeline pode gerar **até 10 PREVIEWS por lote**.

Exemplo:

```text
RODE: LOTE
```

Cada imagem continua independente.

Para assuntos diferentes, o lote não significa uma única imagem com vários assuntos. O sistema usa múltiplas saídas ou várias gerações consecutivas dentro do mesmo turno de ARTE.

Você pode:

```text
APROVAR TODAS
REFAZER SELECIONADAS
REVISAR
CANCELAR
```

Uma imagem rejeitada não obriga a refazer as imagens já aprovadas.

---

## 11. Como funciona uma FOLHA

Uma FOLHA é formada por cards individuais.

O fluxo de uso é:

```text
cards → aprovação → raster dos cards → conferir ornamentos → aplicar nomes → montagem → aprovação da Folha → raster final da Folha
```

A arte dos cards é criada individualmente. A Folha final é montada depois.

Os nomes dos cards são adicionados editorialmente depois da aprovação da ilustração, usando Source Serif 4 Semibold e posicionamento próximo da arte. A ornamentação aprovada é preservada até o final.

---

## 12. Como cancelar

Enquanto um pipeline estiver ativo, `CANCELAR` deve estar disponível em toda pausa.

Digite:

```text
CANCELAR
```

O pipeline termina e preserva o último estado válido. Trabalho já aprovado não deve ser descartado apenas porque o pipeline foi cancelado.

---

## 13. Exemplos rápidos

### Criar a coleção de Relíquias

```text
RODE: RELÍQUIAS
```

Depois use as ações apresentadas pelo pipeline, por exemplo:

```text
GERAR PREVIEWS
APROVAR TODAS
```

### Criar uma Cena

```text
RODE: CENA
```

Descreva o que a cena deve mostrar se isso ainda não estiver definido pelo contexto.

Depois:

```text
APROVAR
```

O pipeline segue para o FINAL RASTER.

### Corrigir apenas um card

```text
RODE: CORRIGIR
```

Informe qual card deve ser alterado. Os demais permanecem preservados.

### Montar cards que já estão aprovados

```text
RODE: MONTAR
```

O pipeline monta a Folha e apresenta a montagem para aprovação.

---

## 14. Regra prática

Para usar o projeto no dia a dia, lembre apenas de três coisas:

```text
1. Comece com RODE: <comando>
2. Escolha uma das ações mostradas durante o pipeline
3. Use CANCELAR se quiser interromper
```

As regras internas de arte, cenário, conteúdo, renderização, montagem e versionamento ficam nos sources do projeto e são aplicadas pelo pipeline quando necessárias.
