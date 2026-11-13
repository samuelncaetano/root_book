# Fase 1: Concepção

| Campo     | Valor            |
| :-------- | :--------------- |
| Projeto   | Root Book        |
| Documento | Índice da Fase 1 |
| Versão    | 0.2              |
| Data      | 12/11/2026       |
| Autor     | Samuel           |
| Status    | Rascunho         |

## Histórico de revisões

| Versão |    Data    | Autor  | Descrição                                                                      |
| :----: | :--------: | :----- | :----------------------------------------------------------------------------- |
|  0.1   | 12/11/2026 | Samuel | Versão inicial.                                                                |
|  0.2   | 12/11/2026 | Samuel | Atualização das versões dos documentos e alinhamento com o cronograma.         |

---

## 1. Objetivo da fase

Definir o problema que o Root Book resolve, verificar a viabilidade do MVP 1 e estabelecer como o projeto será conduzido. A fase termina com a decisão formal de iniciar a Fase 2 (Requisitos).

| Item           | Valor                                                               |
| :------------- | :------------------------------------------------------------------ |
| Período        | 02/11/2026 a 14/11/2026                                             |
| Timebox        | 30 h                                                                |
| Status da fase | Em andamento                                                        |
| Saída          | [Gate da Fase 1](07-gate-fase-1.md) aprovado e tag `concepcao-v1.0` |

---

## 2. Documentos

| Ordem de leitura | Documento                                                  | Conteúdo                                                                   | Versão | Status   |
| :--------------: | :--------------------------------------------------------- | :------------------------------------------------------------------------- | :----: | :------- |
|        1         | [Visão do Produto](01-visao-do-produto-mvp1.md)            | Problema, posicionamento, capacidades candidatas, restrições e roadmap     |  0.2   | Rascunho |
|        2         | [Registro de stakeholders](02-registro-de-stakeholders.md) | Partes interessadas, classificação e engajamento                           |  0.2   | Rascunho |
|        3         | [Estudo de viabilidade](03-estudo-de-viabilidade.md)       | Viabilidade técnica, econômica, de cronograma, legal e operacional         |  0.2   | Rascunho |
|        4         | [Registro de riscos](04-registro-de-riscos.md)             | Riscos, avaliação e respostas                                              |  0.2   | Rascunho |
|        5         | [Termo de abertura](05-termo-de-abertura.md)               | Justificativa, objetivos, escopo, marcos e aprovação                       |  0.2   | Rascunho |
|        6         | [Plano do projeto](06-plano-do-projeto.md)                 | Ciclo de vida, metodologia, cronograma, releases, ambientes e configuração |  0.2   | Rascunho |
|        7         | [Gate da Fase 1](07-gate-fase-1.md)                        | Critérios de saída e decisão                                               |  0.2   | Rascunho |

Os procedimentos que valem para todas as fases estão em [`docs/processo/`](../processo/01-padrao-de-documentos.md).

---

## 3. Relação com as fases seguintes

A Visão do Produto é a principal entrada da Fase 2, na qual as capacidades candidatas (CAP-xx) são analisadas como requisitos. Após o gate, a Visão é congelada e não é mais editada; os requisitos validados passam a constar da SRS em `docs/02-requisitos/`.
