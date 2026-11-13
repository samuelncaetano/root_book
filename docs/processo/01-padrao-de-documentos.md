# Padrão de documentos

| Campo     | Valor                |
| --------- | -------------------- |
| Projeto   | Root Book            |
| Documento | Padrão de documentos |
| Versão    | 1.0                  |
| Data      | 13/11/2026           |
| Autor     | Samuel               |
| Status    | Aprovado             |

## Histórico de revisões

| Versão | Data       | Autor  | Descrição                                                                                                          |
| ------ | ---------- | ------ | ------------------------------------------------------------------------------------------------------------------ |
| 0.1    | 03/11/2026 | Samuel | Versão inicial.                                                                                                    |
| 0.2    | 13/11/2026 | Samuel | Revisão: inclusão do prefixo A-xx (ajuste proposto), usado no estudo de viabilidade, na tabela de identificadores. |
| 1.0    | 13/11/2026 | Samuel | Aprovado no *gate* da Fase 1.                                                                                      |

---

## 1. Propósito

Este documento define a estrutura, o formato, os identificadores e as regras de escrita comuns a todos os documentos do projeto, em todas as fases.

---

## 2. Estrutura de pastas

```text
docs/
├── 01-concepcao/
├── 02-requisitos/
│   └── elicitacao/
├── 03-arquitetura/
│   └── adr/
├── 04-planejamento/
├── 05-desenvolvimento/
│   └── devlog/
├── 06-qualidade/
├── 07-implantacao/
├── 08-operacao/
├── 09-encerramento/
├── processo/
└── sprints/
```

| Pasta                              | Conteúdo                                                                       |
| ---------------------------------- | ------------------------------------------------------------------------------ |
| `01-concepcao` a `09-encerramento` | Documentos de cada fase do ciclo de vida de desenvolvimento de software (SDLC) |
| `processo`                         | Procedimentos que valem para todas as fases                                    |
| `sprints`                          | Planejamento, *review* e retrospectiva de cada *sprint*                        |

---

## 3. Nomes de arquivo

- Nomes em português, em letras minúsculas, sem acentos nem cedilha, com palavras separadas por hífen, por exemplo, `texto-de-exemplo.md`.
- Registros de decisão de arquitetura (ADRs) numerados em sequência, com quatro dígitos, por exemplo, `0001-titulo-da-decisao.md`.
- Registros do *devlog* nomeados pela data no formato AAAA-MM-DD, que mantém a ordem cronológica, por exemplo, `2026-11-03.md`.
- Registros de *sprint* nomeados pelo número, por exemplo, `sprint-01.md`.

---

## 4. Estrutura de um documento

Todo documento tem, nesta ordem:

1. **Título** (`#`), igual ao nome do documento.
2. **Cabeçalho**, em tabela:

   | Campo     | Valor             |
   | --------- | ----------------- |
   | Projeto   | Root Book         |
   | Documento | Nome do documento |
   | Versão    | 0.1               |
   | Data      | DD/MM/AAAA        |
   | Autor     | Samuel            |
   | Status    | Rascunho          |

3. **Histórico de revisões**, em tabela com as colunas Versão, Data, Autor e Descrição, com uma linha por versão, da mais antiga para a mais recente.
4. Uma linha horizontal (`---`) que separa o cabeçalho do conteúdo.
5. Seções numeradas (`## 1. Propósito`, `## 2. ...`).

Os valores de status e de versão seguem o [procedimento de aprovação de documentos](./02-aprovacao-de-documentos.md).

---

## 5. Identificadores

| Prefixo | Uso                              | Documento de origem        |
| ------- | -------------------------------- | -------------------------- |
| CAP-xx  | Capacidade candidata a requisito | Visão do produto           |
| MOD-xx  | Módulo funcional                 | Visão do produto           |
| RN-xx   | Regra de negócio                 | Visão do produto           |
| RQ-xx   | Requisito de qualidade           | Visão do produto           |
| RST-xx  | Restrição                        | Visão do produto           |
| N-xx    | Necessidade de *stakeholder*     | Visão do produto           |
| FL-xx   | Fluxo (cenário de uso)           | Visão do produto           |
| Q-xx    | Questão em aberto                | Registros da Fase 2        |
| STK-xx  | *Stakeholder*                    | Registro de *stakeholders* |
| RSK-xx  | Risco                            | Registro de riscos         |
| M-xx    | Marco                            | Termo de abertura          |
| OBJ-xx  | Objetivo do projeto              | Termo de abertura          |
| R-xx    | Recomendação                     | Estudo de viabilidade      |
| A-xx    | Ajuste proposto                  | Estudo de viabilidade      |

- Os números têm dois dígitos e não são reaproveitados, nem quando o item é removido.
- Todo identificador citado em um documento deve existir no documento de origem.
- As questões em aberto (Q-xx) surgem durante a elicitação e são resolvidas antes do *gate* da fase.

---

## 6. Formato

- Markdown compatível com o GitHub.
- Diagramas em Mermaid, dentro de blocos ` ```mermaid``` `.
- Datas no formato DD/MM/AAAA, exceto nos nomes de arquivo (seção 3).
- Horários no formato de 24 horas, por exemplo, 19:00.
- Números decimais com vírgula, por exemplo, 1,5 h.
- *Links* internos relativos, que apontam para a seção quando necessário, por exemplo, `[Documento](../caminho/documento.md#2-seção)`.

---

## 7. Regras de escrita

- Português formal conforme a norma culta, em linguagem impessoal.
- Sem adjetivos promocionais, como "robusto", "intuitivo" e "poderoso".
- Sem frases de abertura e de fechamento desnecessárias.
- Sem uso excessivo de travessões.
- Sem expressões como "vale ressaltar", "é importante destacar" e "em suma".
- Nenhum dado inventado: valores desconhecidos aparecem como `[A DEFINIR]`.
- Estimativas e recomendações identificadas como tais.
- Tabelas para dados comparáveis; listas para itens que se leem um a um; texto corrido para explicações.
- Palavras estrangeiras não aportuguesadas em itálico, por exemplo, *sprint*, *stakeholder* e *gate*.
