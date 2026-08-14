# O Inferno Verde — Guia de Uso

Este README é um **guia rápido para usar o projeto**.

Você não precisa decorar os arquivos internos nem repetir as regras visuais, de cenário ou de renderização. Use os comandos `RODE:` e o pipeline consulta os sources aplicáveis.

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

## 4. Como aprovar ou pedir mudanças

Quando o pipeline precisar de uma decisão sua, responda usando uma das opções mostradas.

Exemplos comuns:

```text
APROVAR
APROVAR TODAS
REFAZER
AJUSTAR
CORRIGIR CARD
CANCELAR
```

Você não precisa escrever frases completas.

Se apenas um card estiver errado, peça para corrigir esse card. Cards já aprovados devem ser preservados.

---

## 5. PREVIEW e FINAL RASTER

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

## 6. O que conta como PREVIEW válida

A PREVIEW deve ser **a própria imagem que está sendo produzida**.

Não são PREVIEWS válidas:

- dashboards;
- infográficos;
- mockups de pipeline;
- folhas de contato;
- imagens mostrando miniaturas do trabalho;
- cards desenhados dentro de uma interface fictícia.

Se você pediu oito cards, as PREVIEWS devem ser **oito imagens reais e independentes**, não uma imagem contendo oito miniaturas.

---

## 7. Lotes de imagens

Quando houver várias imagens independentes, o pipeline pode gerar **até 10 PREVIEWS por lote**.

Exemplo:

```text
RODE: LOTE
```

Cada imagem continua independente.

Você pode:

```text
APROVAR TODAS
REFAZER SELECIONADAS
REVISAR
CANCELAR
```

Uma imagem rejeitada não obriga a refazer as imagens já aprovadas.

---

## 8. Como funciona uma FOLHA

Uma FOLHA é formada por cards individuais.

O fluxo de uso é:

```text
cards → aprovação → raster dos cards → montagem → aprovação da Folha → raster final da Folha
```

A arte dos cards é criada individualmente. A Folha final é montada depois.

Os nomes dos cards são adicionados na montagem, não durante a geração da ilustração.

---

## 9. Como cancelar

Enquanto um pipeline estiver ativo, `CANCELAR` deve estar disponível em toda pausa.

Digite:

```text
CANCELAR
```

O pipeline termina e preserva o último estado válido. Trabalho já aprovado não deve ser descartado apenas porque o pipeline foi cancelado.

---

## 10. Exemplos rápidos

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

## 11. Regra prática

Para usar o projeto no dia a dia, lembre apenas de três coisas:

```text
1. Comece com RODE: <comando>
2. Escolha uma das ações mostradas durante o pipeline
3. Use CANCELAR se quiser interromper
```

As regras internas de arte, cenário, conteúdo, renderização, montagem e versionamento ficam nos sources do projeto e são aplicadas pelo pipeline quando necessárias.
