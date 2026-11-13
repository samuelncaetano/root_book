# Gate da Fase 1: Concepção

| Campo     | Valor          |
| --------- | -------------- |
| Projeto   | Root Book      |
| Documento | Gate da Fase 1 |
| Versão    | 1.0            |
| Data      | 13/11/2026     |
| Autor     | Samuel         |
| Status    | Aprovado       |

## Histórico de revisões

| Versão | Data       | Autor  | Descrição                                                                                                                                                                                                            |
| ------ | ---------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0.1    | 12/11/2026 | Samuel | Versão inicial.                                                                                                                                                                                                      |
| 0.2    | 12/11/2026 | Samuel | Atualização da data prevista do *gate* para 14/11/2026 (marco M-02).                                                                                                                                                 |
| 0.3    | 12/11/2026 | Samuel | Correção do status da Visão do Produto para "Congelado (*baseline*)", conforme o procedimento de aprovação.                                                                                                          |
| 0.4    | 13/11/2026 | Samuel | Inclusão das pendências apontadas na revisão da Fase 1 (#11) e dos valores `[A DEFINIR]` do README da raiz; status ajustado para "Aguardando aprovação", conforme o ciclo de vida; palavras estrangeiras em itálico. |
| 1.0    | 13/11/2026 | Samuel | Aprovado no *gate* da Fase 1.                                                                                                                                                                                        |

---

## 1. Objetivo

Verificar se a Fase 1 produziu o necessário para iniciar a Fase 2 e registrar a decisão do patrocinador. Data prevista: 14/11/2026 (marco M-02).

## 2. Critérios de saída

| #   | Critério                                                                                                                 | Evidência                                                                       | Atendido |
| --- | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------- | -------- |
| 1   | O problema está declarado e o posicionamento está registrado                                                             | [Visão, seção 2](01-visao-do-produto-mvp1.md#2-posicionamento)                  | [x]      |
| 2   | A Visão do Produto foi revisada e está pronta para congelamento                                                          | [Visão do Produto](01-visao-do-produto-mvp1.md)                                 | [x]      |
| 3   | As capacidades candidatas do MVP 1 estão identificadas e não há questões em aberto sobre capacidades e regras de negócio | [Visão, seção 6](01-visao-do-produto-mvp1.md#6-capacidades)                     | [x]      |
| 4   | Os *stakeholders* estão identificados, classificados e com estratégia de engajamento                                     | [Registro de *stakeholders*](02-registro-de-stakeholders.md)                    | [x]      |
| 5   | O estudo de viabilidade está concluído, com resultado registrado                                                         | [Estudo de viabilidade, seção 7](03-estudo-de-viabilidade.md#7-conclusão-geral) | [x]      |
| 6   | Os riscos estão identificados, avaliados e com resposta definida                                                         | [Registro de riscos](04-registro-de-riscos.md)                                  | [x]      |
| 7   | O termo de abertura está aprovado pelo patrocinador                                                                      | [Termo de abertura, seção 10](05-termo-de-abertura.md#10-aprovação)             | [x]      |
| 8   | O plano do projeto está definido                                                                                         | [Plano do projeto](06-plano-do-projeto.md)                                      | [x]      |
| 9   | A estratégia da instância de demonstração está definida                                                                  | [Plano do projeto, seção 9](06-plano-do-projeto.md#9-instância-de-demonstração) | [x]      |
| 10  | O repositório está configurado                                                                                           | *Issue* de configuração do repositório fechada                                  | [x]      |
| 11  | As decisões pendentes estão registradas com prazo                                                                        | Seção 3 deste documento                                                         | [x]      |

## 3. Pendências conhecidas

Pendências que não impedem a saída da fase, com prazo para resolução.

| Pendência                   | Descrição                                                                                                                                      | Prazo                         |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| Recorte do MVP 1            | Confirmação, pela priorização MoSCoW, das capacidades indicadas para o MVP 1, com limite de 126 h                                              | Fase 2                        |
| Prova de conceito           | Seleção de intervalos no calendário                                                                                                            | Fase 3                        |
| *Releases* seguintes        | Escopo e datas das *releases* após o MVP 1                                                                                                     | Após a entrega do MVP 1       |
| Demonstração no README      | *Link* da instância de demonstração e credenciais da conta de exemplo, hoje `[A DEFINIR]` no README da raiz                                    | *Release* 0.2.0 (09/01/2027)  |
| Risco de fuso horário       | No estudo de viabilidade, a conversão entre UTC e o fuso do usuário aponta para o RSK-02, e o registro de riscos não tem risco de fuso horário | *Gate* da Fase 2 (28/11/2026) |
| Horas da estabilização      | A estabilização (25/01 a 31/01/2027) tem 6 dias úteis e 20 h, sem justificativa em relação às 30 h da disponibilidade de 5 h por dia           | *Gate* da Fase 2 (28/11/2026) |
| Data dos marcos M-07 e M-08 | 31/01/2027 é um domingo, fora da jornada de segunda a sábado; a alteração exige aprovação do patrocinador                                      | *Gate* da Fase 2 (28/11/2026) |

## 4. Decisão

| Opção                                      | Marcar |
| ------------------------------------------ | ------ |
| Aprovar e iniciar a Fase 2                 | [ ]    |
| Aprovar com ressalvas e iniciar a Fase 2   | [x]    |
| Reprovar e revisar os documentos da Fase 1 | [ ]    |

| Campo                   | Valor                                                                                                                                                                                                                                                                                           |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Decisão                 | Aprovar com ressalvas e iniciar a Fase 2                                                                                                                                                                                                                                                        |
| Data                    | 13/11/2026                                                                                                                                                                                                                                                                                      |
| Responsável             | Samuel (patrocinador)                                                                                                                                                                                                                                                                           |
| Ressalvas e observações | O *gate* foi antecipado para 13/11/2026, um dia antes do marco M-02 (14/11/2026), e o PR da revisão (#23) foi revisado no mesmo dia da abertura, e não no dia útil seguinte, como define a seção 3.3 do plano do projeto. As pendências da seção 3 permanecem abertas, com os prazos indicados. |

## 5. Ações após a aprovação

Os passos detalhados estão no [procedimento de aprovação de documentos](../processo/02-aprovacao-de-documentos.md#4-parte-b-gate-da-fase).

1. Passar os documentos da fase para a versão 1.0, com status "Aprovado"; a Visão do Produto recebe o status "Congelado (*baseline*)".
2. Registrar a decisão e a data no termo de abertura.
3. Atualizar o [README da pasta](README.md) e o README da raiz, com a Fase 1 como "Concluída".
4. Fazer o *merge* do PR do *gate* e criar a *tag* `concepcao-v1.0`.
5. Registrar no *devlog* a data do *gate* e o total de horas da fase.
6. Iniciar a Fase 2 pelo plano de elicitação.
