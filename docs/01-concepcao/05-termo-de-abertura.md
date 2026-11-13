# Termo de Abertura do Projeto

| Campo     | Valor                        |
| --------- | ---------------------------- |
| Projeto   | Root Book                    |
| Documento | Termo de Abertura do Projeto |
| Versão    | 0.4                          |
| Data      | 13/11/2026                   |
| Autor     | Samuel                       |
| Status    | Aguardando aprovação         |

## Histórico de revisões

| Versão | Data       | Autor  | Descrição                                                                                            |
| ------ | ---------- | ------ | ---------------------------------------------------------------------------------------------------- |
| 0.1    | 12/11/2026 | Samuel | Versão inicial.                                                                                      |
| 0.2    | 12/11/2026 | Samuel | Ajuste das datas de marcos, cronograma e término previsto do MVP 1 para 31/01/2027.                  |
| 0.3    | 12/11/2026 | Samuel | Ajuste da disponibilidade para 15 h semanais nas Fases 1 a 4 e 30 h semanais na construção do MVP 1. |
| 0.4    | 13/11/2026 | Samuel | Revisão: palavras estrangeiras em itálico, conforme o padrão de documentos.                          |

---

## 1. Identificação

| Item                      | Descrição                                                                                                                 |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Projeto                   | Root Book: software web de planejamento pessoal                                                                           |
| Patrocinador              | Samuel                                                                                                                    |
| Gerente do projeto        | Samuel                                                                                                                    |
| Equipe                    | Samuel, em todos os papéis técnicos                                                                                       |
| Vínculo do autor          | Universidade de Brasília (UnB), Faculdade de Ciências e Tecnologias em Engenharia (FCTE), curso de Engenharia de Software |
| Início                    | 02/11/2026                                                                                                                |
| Término previsto do MVP 1 | 31/01/2027                                                                                                                |
| Orçamento                 | R$ 0                                                                                                                      |

O gerente do projeto tem autoridade para alocar as horas do projeto, priorizar o escopo dentro dos objetivos deste termo e aprovar mudanças que não alterem os marcos M-05 e M-07. Mudanças nesses marcos exigem nova aprovação do patrocinador.

## 2. Justificativa

Pessoas com rotina variada costumam usar um calendário para os compromissos e uma lista separada para as tarefas, sem reservar no calendário o tempo necessário para executá-las. O Root Book propõe reunir eventos, tarefas e blocos de tempo no mesmo calendário. A descrição completa do problema e do posicionamento está na [Visão do Produto](01-visao-do-produto-mvp1.md#2-posicionamento).

O projeto também é o principal trabalho de portfólio do autor para candidaturas a estágio em Engenharia de Software no semestre 2027.1 da UnB. Por isso, o processo de engenharia, e não apenas o produto, é parte do resultado esperado.

## 3. Objetivos

| ID     | Objetivo                                                             | Indicador                                                                        | Prazo      |
| ------ | -------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ---------- |
| OBJ-01 | Concluir a documentação das Fases 1 a 4, com *baseline* de cada fase | *Tags* de *baseline* das quatro fases criadas no repositório                     | 26/12/2026 |
| OBJ-02 | Publicar a aplicação mínima na instância de demonstração             | *Link* público respondendo, com *deploy* automático a partir da `main`           | 02/01/2027 |
| OBJ-03 | Publicar o MVP 1 (1.0.0) com as capacidades *Must*                   | Todas as capacidades *Must* da SRS implementadas e aceitas                       | 31/01/2027 |
| OBJ-04 | Cobrir os fluxos do MVP 1 com testes de ponta a ponta no CI          | Fluxos do MVP 1 executados no CI sem falhas na versão 1.0.0                      | 31/01/2027 |
| OBJ-05 | Atender os requisitos de qualidade mensuráveis do MVP 1              | Cada requisito de qualidade mensurável verificado pelo método definido na Fase 2 | 31/01/2027 |
| OBJ-06 | Publicar instruções de execução do projeto com Docker Compose        | Execução concluída em ambiente limpo seguindo apenas as instruções publicadas    | 31/01/2027 |

## 4. Requisitos de alto nível

As capacidades candidatas estão na [Visão do Produto, seção 6](01-visao-do-produto-mvp1.md#6-capacidades) e serão validadas e priorizadas na Fase 2. As indicadas para o MVP 1 se agrupam assim:

| Requisito                                 | Capacidades                                |
| ----------------------------------------- | ------------------------------------------ |
| Conta, autenticação e isolamento de dados | CAP-01, CAP-02, CAP-04                     |
| Privacidade conforme a LGPD               | CAP-05, CAP-07                             |
| Organização em Espaços                    | CAP-08 (parcial)                           |
| Calendário e eventos                      | CAP-12 (parcial), CAP-13 (parcial), CAP-14 |
| Tarefas                                   | CAP-20 a CAP-22                            |
| Reserva de horário livre para uma tarefa  | CAP-26, CAP-27, CAP-29 (parcial), CAP-31   |
| Datas, validação e logs                   | CAP-43, CAP-52, CAP-53                     |
| Modo demonstração                         | CAP-54                                     |

## 5. Escopo

### 5.1 Entregáveis

- MVP 1 na versão 1.0.0, com código-fonte no repositório público `root_book`.
- Instância de demonstração pública, em modo demonstração, com conta de exemplo e dados fictícios.
- Instruções de execução com Docker Compose.
- Termos de uso e política de privacidade.
- Documentação de cada fase do ciclo de desenvolvimento, em `docs/`.
- README da raiz do repositório.

### 5.2 Exclusões

As capacidades indicadas como Posterior e os itens listados na [Visão do Produto, seção 11](01-visao-do-produto-mvp1.md#11-fora-do-escopo) não fazem parte do MVP 1.

## 6. Premissas e restrições

### 6.1 Premissas

- O autor dispõe, de segunda a sábado, de 15 horas semanais nas Fases 1 a 4 e de 30 horas semanais na construção do MVP 1.
- O período de 18/01 a 31/01/2027 é usado como Sprint 4 e estabilização, conforme o estudo de viabilidade.
- Os planos gratuitos dos fornecedores permanecem disponíveis durante o projeto.
- O autor tem domínio da stack definida.

### 6.2 Restrições

- Uma única pessoa, sem participação de terceiros em nenhuma atividade.
- Orçamento zero.
- MVP 1 publicado até 31/01/2027.
- Stack: TypeScript, Next.js, NestJS, PostgreSQL, Prisma ORM, Testcontainers, Vitest, SWC, Zod e JWT.
- Conformidade com a LGPD.

As demais restrições estão na [Visão do Produto, seção 9](01-visao-do-produto-mvp1.md#9-restrições).

## 7. Marcos

| ID   | Marco                                                                             | Data       |
| ---- | --------------------------------------------------------------------------------- | ---------- |
| M-01 | Início do projeto                                                                 | 02/11/2026 |
| M-02 | Gate da Fase 1: concepção aprovada                                                | 14/11/2026 |
| M-03 | Gate da Fase 2: *baseline* de requisitos                                          | 28/11/2026 |
| M-04 | Gate da Fase 3: *baseline* de arquitetura                                         | 12/12/2026 |
| M-05 | Gate da Fase 4: documentação das Fases 1 a 4 concluída                            | 26/12/2026 |
| M-06 | Primeiro *deploy* da instância de demonstração (*release* 0.1.0, fim da Sprint 1) | 02/01/2027 |
| M-07 | MVP 1 (*release* 1.0.0)                                                           | 31/01/2027 |
| M-08 | Retrospectiva do MVP 1                                                            | 31/01/2027 |

## 8. Riscos principais

O registro completo está no [registro de riscos](04-registro-de-riscos.md).

| ID     | Risco                                                                        | Exposição |
| ------ | ---------------------------------------------------------------------------- | --------- |
| RSK-01 | Escopo do MVP 1 excede a capacidade das *sprints*                            | Alta (16) |
| RSK-13 | Usuário acessa dados de outro usuário                                        | Alta (15) |
| RSK-02 | Seleção no calendário e reserva de blocos consomem mais tempo que o estimado | Alta (12) |
| RSK-03 | Atividades acadêmicas e feriados reduzem as horas disponíveis                | Alta (12) |
| RSK-04 | Documentação das Fases 1 a 4 excede 120 h                                    | Alta (12) |
| RSK-08 | Visitante interpreta a hibernação da demonstração como falha                 | Alta (12) |

## 9. Critérios de sucesso

O MVP 1 é considerado bem-sucedido quando, até 31/01/2027:

1. Um usuário consegue registrar eventos e tarefas e reservar um horário livre da semana para uma tarefa.
2. A versão 1.0.0 está acessível pelo *link* público da demonstração, com a conta de exemplo.
3. Os objetivos OBJ-01 a OBJ-06 foram atingidos.
4. A documentação de cada fase está publicada no repositório e reflete o que foi construído.

## 10. Aprovação

| Papel        | Nome   | Decisão     | Data        |
| ------------ | ------ | ----------- | ----------- |
| Patrocinador | Samuel | [A DEFINIR] | [A DEFINIR] |

Com a aprovação, o projeto é formalmente iniciado e o gerente do projeto fica autorizado a aplicar os recursos descritos neste termo.
