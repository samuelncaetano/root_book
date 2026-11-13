# Fase 1: Concepção

| Campo     | Valor            |
| :-------- | :--------------- |
| Projeto   | Root Book        |
| Documento | Índice da Fase 1 |
| Versão    | 1.0              |
| Data      | 13/11/2026       |
| Autor     | Samuel           |
| Status    | Aprovado         |

## Histórico de revisões

| Versão |    Data    | Autor  | Descrição                                                                                                                         |
| :----: | :--------: | :----- | :-------------------------------------------------------------------------------------------------------------------------------- |
|  0.1   | 12/11/2026 | Samuel | Versão inicial.                                                                                                                   |
|  0.2   | 12/11/2026 | Samuel | Atualização das versões dos documentos e alinhamento com o cronograma.                                                            |
|  0.3   | 13/11/2026 | Samuel | Revisão: atualização das versões e dos status dos documentos e palavras estrangeiras em itálico, conforme o padrão de documentos. |
|  1.0   | 13/11/2026 | Samuel | Aprovado no *gate* da Fase 1.                                                                                                     |

---

## 1. Objetivo da fase

Definir o problema que o Root Book resolve, verificar a viabilidade do MVP 1 e estabelecer como o projeto será conduzido. A fase termina com a decisão formal de iniciar a Fase 2 (Requisitos).

| Item           | Valor                                                                 |
| :------------- | :-------------------------------------------------------------------- |
| Período        | 02/11/2026 a 14/11/2026                                               |
| *Timebox*      | 30 h                                                                  |
| Status da fase | Concluída                                                             |
| Saída          | [Gate da Fase 1](07-gate-fase-1.md) aprovado e *tag* `concepcao-v1.0` |

---

## 2. Documentos

| Ordem de leitura | Documento                                                    | Conteúdo                                                                     | Versão | Status                 |
| :--------------: | :----------------------------------------------------------- | :--------------------------------------------------------------------------- | :----: | :--------------------- |
|        1         | [Visão do Produto](01-visao-do-produto-mvp1.md)              | Problema, posicionamento, capacidades candidatas, restrições e roadmap       |  1.0   | Congelado (*baseline*) |
|        2         | [Registro de *stakeholders*](02-registro-de-stakeholders.md) | Partes interessadas, classificação e engajamento                             |  1.0   | Aprovado               |
|        3         | [Estudo de viabilidade](03-estudo-de-viabilidade.md)         | Viabilidade técnica, econômica, de cronograma, legal e operacional           |  1.0   | Aprovado               |
|        4         | [Registro de riscos](04-registro-de-riscos.md)               | Riscos, avaliação e respostas                                                |  1.0   | Aprovado               |
|        5         | [Termo de abertura](05-termo-de-abertura.md)                 | Justificativa, objetivos, escopo, marcos e aprovação                         |  1.0   | Aprovado               |
|        6         | [Plano do projeto](06-plano-do-projeto.md)                   | Ciclo de vida, metodologia, cronograma, *releases*, ambientes e configuração |  1.0   | Aprovado               |
|        7         | [Gate da Fase 1](07-gate-fase-1.md)                          | Critérios de saída e decisão                                                 |  1.0   | Aprovado               |

Os procedimentos que valem para todas as fases estão em [`docs/processo/`](../processo/01-padrao-de-documentos.md).

---

## 3. Relação com as fases seguintes

A Visão do Produto é a principal entrada da Fase 2, na qual as capacidades candidatas (CAP-xx) são analisadas como requisitos. Após o *gate*, a Visão é congelada e não é mais editada; os requisitos validados passam a constar da SRS em `docs/02-requisitos/`.
