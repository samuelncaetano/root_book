# Estudo de Viabilidade

| Campo     | Valor                 |
| --------- | --------------------- |
| Projeto   | Root Book             |
| Documento | Estudo de Viabilidade |
| Versão    | 0.4                   |
| Data      | 13/11/2026            |
| Autor     | Samuel                |
| Status    | Aguardando aprovação  |

## Histórico de revisões

| Versão | Data       | Autor  | Descrição                                                                                              |
| ------ | ---------- | ------ | ------------------------------------------------------------------------------------------------------ |
| 0.1    | 12/11/2026 | Samuel | Versão inicial.                                                                                        |
| 0.2    | 12/11/2026 | Samuel | Ajuste das datas de cronograma com adição de uma semana a cada fase e entrega do MVP 1 até 31/01/2027. |
| 0.3    | 12/11/2026 | Samuel | Ajuste da disponibilidade para 15 h semanais nas Fases 1 a 4 e 30 h semanais na construção do MVP 1.   |
| 0.4    | 13/11/2026 | Samuel | Revisão: palavras estrangeiras em itálico, conforme o padrão de documentos.                            |

---

## 1. Propósito e escopo

Este estudo avalia se o MVP 1 descrito na [Visão do Produto](01-visao-do-produto-mvp1.md) pode ser realizado com uma pessoa, 15 horas semanais nas Fases 1 a 4, 30 horas semanais na construção e orçamento zero até 31/01/2027. São analisadas as viabilidades técnica, econômica, de cronograma, legal e operacional.

As estimativas foram feitas na concepção, sem histórico de velocidade do autor, e têm incerteza estimada de ±30%. Elas serão refinadas após a Fase 3 e após a Sprint 1.

---

## 2. Viabilidade técnica

### 2.1 Stack definida

O autor declara domínio de todos os itens abaixo.

| Componente     | Uso no projeto                           | Pontos de atenção                                                                    |
| -------------- | ---------------------------------------- | ------------------------------------------------------------------------------------ |
| TypeScript     | Linguagem de todo o código               | Configuração compartilhada entre front-end, API e pacotes comuns                     |
| Next.js        | Front-end                                | Encaminhamento de `/api` para a API; calendário interativo renderizado no cliente    |
| NestJS         | API                                      | Compilação com SWC preservando os metadados dos *decorators*                         |
| PostgreSQL     | Banco de dados                           | Consultas por intervalo de datas                                                     |
| Prisma ORM     | Acesso a dados e migrações               | Uso com o *pooler* do Neon na demonstração; migrações executadas no comando de start |
| Testcontainers | Testes de integração com PostgreSQL real | Exige Docker no CI, disponível nos runners Linux do GitHub Actions                   |
| Vitest         | Testes unitários e de integração         | Integração com SWC para os testes do NestJS                                          |
| SWC            | Compilação                               | Suporte a *decorators* e metadados de tipo                                           |
| Zod            | Validação                                | Compartilhamento de esquemas entre front-end e API                                   |
| JWT            | Autenticação                             | Local de armazenamento do *token*, expiração e revogação; decisão em ADR na Fase 3   |

### 2.2 Componentes complementares propostos

A adoção de cada componente será confirmada por ADR na Fase 3.

| Componente                                        | Finalidade                                                |
| ------------------------------------------------- | --------------------------------------------------------- |
| pnpm workspaces e Turborepo                       | *Monorepo* e execução de tarefas                          |
| ESLint, Prettier, Husky, lint-staged e commitlint | Padronização de código e de mensagens de *commit*         |
| Playwright e axe-core                             | Testes de ponta a ponta e de acessibilidade               |
| k6                                                | Verificação do RQ-02                                      |
| @nestjs/swagger                                   | Contrato OpenAPI                                          |
| Argon2 e Passport JWT                             | Hash de senhas e autenticação                             |
| Pino                                              | Logs estruturados (CAP-53)                                |
| date-fns-tz                                       | Conversão de fusos (CAP-43)                               |
| Tailwind CSS e shadcn/ui                          | Interface                                                 |
| FullCalendar                                      | Visão de calendário, restrito aos recursos de licença MIT |
| Docker Compose e GitHub Actions                   | Execução local e integração contínua                      |
| Mailpit                                           | Captura de e-mails em desenvolvimento                     |

### 2.3 Pontos de maior risco técnico

| Ponto                                                                   | Capacidades            | Tratamento                                                                           | Risco  |
| ----------------------------------------------------------------------- | ---------------------- | ------------------------------------------------------------------------------------ | ------ |
| Seleção de intervalo no calendário e abertura da paleta sobre a seleção | CAP-26, CAP-27, CAP-31 | Prova de conceito com FullCalendar na Fase 3 (*timebox* de 6 h)                      | RSK-02 |
| Autorização por usuário em todas as consultas                           | CAP-04                 | Filtro por usuário centralizado na API e testes automatizados de acesso indevido     | RSK-13 |
| Conversão entre UTC e o fuso do usuário                                 | CAP-43                 | Testes unitários com datas próximas da meia-noite e de outros fusos                  | RSK-02 |
| Hibernação da API e do banco na demonstração                            | CAP-54                 | Aviso de inicialização; *endpoint* `/health` sem consulta ao banco                   | RSK-08 |
| Migrações no comando de start                                           | Todas                  | Migrações compatíveis com a versão anterior; procedimento de *rollback* no *runbook* | RSK-15 |

### 2.4 Conclusão técnica

Viável. A interação de seleção no calendário depende de prova de conceito na Fase 3. Se a prova de conceito não for concluída dentro do *timebox*, o escopo das capacidades CAP-26 e CAP-27 deve ser revisto antes da Fase 4.

---

## 3. Viabilidade econômica

### 3.1 Custos

| Item                           | Solução                                                           | Custo               |
| ------------------------------ | ----------------------------------------------------------------- | ------------------- |
| Trabalho                       | Horas do autor                                                    | Sem custo monetário |
| Repositório, gestão e CI       | GitHub (repositório público), GitHub Projects e GitHub Actions    | R$ 0                |
| Ferramentas de desenvolvimento | Ferramentas de código aberto da seção 2                           | R$ 0                |
| Protótipos                     | Figma, plano gratuito                                             | R$ 0                |
| Instância de demonstração      | Planos gratuitos de Vercel, Render e Neon                         | R$ 0                |
| Domínio                        | Não adquirido; uso dos subdomínios gratuitos dos fornecedores     | R$ 0                |
| E-mail                         | Não usado no MVP 1 (CAP-03 posterior); Mailpit em desenvolvimento | R$ 0                |
| **Total**                      |                                                                   | **R$ 0**            |

### 3.2 Limites dos planos gratuitos

Data de consulta: 28/10/2026. Os limites mudam com o tempo e devem ser conferidos novamente no primeiro *deploy*.

| Serviço              | Uso                    | Limites relevantes                                                                                                                                                                                                                                            |
| -------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Vercel Hobby         | Front-end              | Uso pessoal e não comercial; 100 GB de transferência por mês; 1 milhão de invocações de função por mês                                                                                                                                                        |
| Render Free          | API                    | Hiberna após 15 min sem tráfego e leva cerca de 1 min para voltar; 750 h de instância por mês por workspace, sem acúmulo; serviços gratuitos suspensos ao exceder a franquia de banda quando não há meio de pagamento cadastrado; sem comando de *pre-deploy* |
| Render Postgres Free | Não usado              | O banco expira 30 dias após a criação                                                                                                                                                                                                                         |
| Neon Free            | Banco de dados         | 1 GB de armazenamento por projeto; 100 CU-horas por mês por projeto; suspensão após 5 min ocioso; sem backups agendados                                                                                                                                       |
| GitHub Actions       | CI e rotinas agendadas | Gratuito para repositórios públicos; agendamentos desativados após 60 dias sem atividade no repositório                                                                                                                                                       |

### 3.3 Estimativa de consumo da instância de demonstração

| Recurso                                        | Premissa                                                                                                                                | Consumo estimado       | Limite                |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- |
| Horas de instância no Render, sem *keep-alive* | Ativa apenas durante as visitas                                                                                                         | Muito abaixo do limite | 750 h/mês             |
| Horas de instância no Render, com *keep-alive* | Ativa o mês inteiro (31 dias)                                                                                                           | 744 h/mês              | 750 h/mês             |
| CU-horas do Neon                               | Compute mínimo de 0,25 CU; reinício diário de cerca de 10 min; 100 sessões de visitantes por mês, com cerca de 20 min de atividade cada | Cerca de 10 CU-h/mês   | 100 CU-h/mês          |
| CU-horas do Neon com o banco sempre ativo      | 744 h × 0,25 CU                                                                                                                         | 186 CU-h/mês           | 100 CU-h/mês (excede) |
| Armazenamento no Neon                          | Uma conta de exemplo com dados fictícios                                                                                                | Na ordem de megabytes  | 1 GB                  |

Conclusões da estimativa:

- Apenas um serviço do Render pode permanecer ativo durante o mês inteiro.
- O banco não deve ser mantido ativo; por isso, o *endpoint* `/health` não consulta o banco.
- Sem meio de pagamento cadastrado, o excesso de uso resulta em suspensão do serviço, e não em cobrança.

### 3.4 Conclusão econômica

Viável com custo zero, condicionado à manutenção dos planos gratuitos (RSK-06) e ao consumo dentro das cotas (RSK-07).

---

## 4. Viabilidade de cronograma

### 4.1 Capacidade

Disponibilidade de segunda a sábado: 15 horas semanais (2,5 horas por dia) nas Fases 1 a 4, em paralelo ao semestre letivo da UnB, e 30 horas semanais (5 horas por dia) na construção do MVP 1.

| Período                     | Atividade                                                     | Dias úteis | Horas   |
| --------------------------- | ------------------------------------------------------------- | ---------- | ------- |
| 02/11 a 14/11/2026          | Fase 1: Concepção                                             | 12         | 30      |
| 16/11 a 28/11/2026          | Fase 2: Requisitos                                            | 12         | 30      |
| 30/11 a 12/12/2026          | Fase 3: Arquitetura                                           | 12         | 30      |
| 14/12 a 26/12/2026          | Fase 4: Planejamento da execução                              | 12         | 30      |
| **02/11 a 26/12/2026**      | **Documentação (Fases 1 a 4)**                                | **48**     | **120** |
| 28/12/2026 a 02/01/2027     | Sprint 1                                                      | 6          | 30      |
| 04/01 a 09/01/2027          | Sprint 2                                                      | 6          | 30      |
| 11/01 a 16/01/2027          | Sprint 3                                                      | 6          | 30      |
| 18/01 a 23/01/2027          | Sprint 4 (recomendação)                                       | 6          | 30      |
| 25/01 a 31/01/2027          | Estabilização, *release* 1.0.0 e retrospectiva (recomendação) | 6          | 20      |
| **28/12/2026 a 31/01/2027** | **Construção do MVP 1**                                       | **30**     | **140** |

### 4.2 Uso do período de 18/01 a 31/01/2027

**Recomendação:** usar o período até o prazo do MVP 1 como uma quarta *sprint* (18/01 a 23/01/2027) e uma etapa de estabilização (25/01 a 31/01/2027), dedicada à *release* 1.0.0, às instruções de execução e à retrospectiva. Sem esse período, a capacidade de construção cai para 90 h, insuficiente para o recorte indicado na seção 4.4.

### 4.3 Feriados

O cálculo considera os feriados como dias de trabalho. Cada feriado não trabalhado reduz a capacidade em 2,5 horas nas Fases 1 a 4 e em 5 horas nas *sprints*.

| Data       | Feriado                                      | Período afetado |
| ---------- | -------------------------------------------- | --------------- |
| 02/11/2026 | Finados                                      | Fase 1          |
| 20/11/2026 | Dia Nacional de Zumbi e da Consciência Negra | Fase 2          |
| 25/12/2026 | Natal                                        | Fase 4          |
| 01/01/2027 | Confraternização Universal                   | Sprint 1        |

Durante as Fases 1 a 4, o semestre letivo da UnB está em andamento, o que pode reduzir a disponibilidade real (RSK-03).

### 4.4 Esforço do MVP 1

Estimativa preliminar por decomposição, para as capacidades indicadas como MVP 1 na [Visão do Produto](01-visao-do-produto-mvp1.md#6-capacidades), incluindo implementação, testes automatizados e documentação de cada item.

| Item                                                                                     | Capacidades                                | Estimativa (h) |
| ---------------------------------------------------------------------------------------- | ------------------------------------------ | -------------- |
| Fundação: *monorepo*, qualidade de código, CI, Docker Compose e *deploy* na demonstração |                                            | 28             |
| MOD-01 Autenticação                                                                      | CAP-01, CAP-02                             | 12             |
| MOD-02 Autorização                                                                       | CAP-04                                     | 8              |
| MOD-03 Conta e privacidade                                                               | CAP-05, CAP-07                             | 6              |
| MOD-04 Organização                                                                       | CAP-08 (parcial)                           | 5              |
| MOD-05 Calendário                                                                        | CAP-12 (parcial), CAP-13 (parcial), CAP-14 | 16             |
| MOD-07 Tarefas                                                                           | CAP-20 a CAP-22                            | 12             |
| MOD-08 Planejamento                                                                      | CAP-26, CAP-27, CAP-29 (parcial), CAP-31   | 12             |
| MOD-10 Fuso horário e datas                                                              | CAP-43                                     | 3              |
| MOD-14 Validação e erros                                                                 | CAP-52                                     | 3              |
| MOD-15 Observabilidade                                                                   | CAP-53                                     | 3              |
| MOD-16 Demonstração, *seed* e reinício diário                                            | CAP-54                                     | 8              |
| Testes de ponta a ponta dos fluxos do MVP 1 e testes não funcionais                      |                                            | 8              |
| Documentação das Fases 5 a 8                                                             |                                            | 6              |
| Cerimônias de *sprint* (4 *sprints* × 1,5 h)                                             |                                            | 6              |
| **Total estimado**                                                                       |                                            | **136**        |

| Indicador                    | Horas  |
| ---------------------------- | ------ |
| Capacidade de construção     | 140    |
| Reserva recomendada (10%)    | 14     |
| Capacidade planejável        | 126    |
| Estimativa do MVP 1 indicado | 136    |
| **Diferença**                | **10** |

### 4.5 Ajustes propostos

**A-01.** Na priorização MoSCoW da Fase 2, limitar as capacidades *Must* do MVP 1 a 126 horas estimadas.

**A-02.** Candidatas a *Could*, adiáveis se a velocidade da Sprint 1 ficar abaixo do planejado:

| Item                  | Parte candidata ao adiamento                                   | Estimativa (h) |
| --------------------- | -------------------------------------------------------------- | -------------- |
| CAP-53                | Logs estruturados                                              | 3              |
| CAP-07                | Exclusão da conta                                              | 4              |
| Testes não funcionais | Teste de carga com k6, mantida a verificação de acessibilidade | 3              |
| **Total**             |                                                                | **10**         |

**A-03.** Reestimar o MVP 1 após a Fase 3, com a arquitetura definida, e após a Sprint 1, com a velocidade real medida.

As capacidades indicadas como Posterior não foram estimadas nesta fase; a estimativa será feita no planejamento das *releases* seguintes.

### 4.6 Conclusão de cronograma

Viável com ajustes. O prazo de 31/01/2027 é exequível com o uso do período de 18/01 a 31/01/2027 (seção 4.2) e o limite de escopo da A-01.

---

## 5. Viabilidade legal

Análise preliminar, sem caráter de parecer jurídico.

### 5.1 LGPD

**Papéis.** Na instância de demonstração, o autor é o responsável pelo tratamento dos dados. Quem executar o projeto com dados reais em instância própria responde pelo tratamento desses dados.

**Obrigações e capacidades do MVP 1:**

| Obrigação                    | Capacidade | Situação no MVP 1                          |
| ---------------------------- | ---------- | ------------------------------------------ |
| Consentimento                | CAP-05     | Incluída                                   |
| Eliminação                   | CAP-07     | Incluída (candidata a adiamento pela A-02) |
| Acesso e portabilidade       | CAP-06     | Posterior                                  |
| Segurança                    | RQ-03      | Incluída                                   |
| Minimização de dados em logs | CAP-53     | Incluída                                   |

Enquanto a exportação (CAP-06) não existir, o README deve informar que a *release* não atende ao direito de portabilidade, para que quem executar o projeto com dados reais saiba da limitação.

**Instância de demonstração.** Os fornecedores armazenam dados fora do Brasil. O modo demonstração (CAP-54) desativa o cadastro, de modo que a instância não coleta dados pessoais de visitantes. Permanece um ponto residual: os registros de acesso mantidos pelos fornecedores, como endereços IP, que a política de privacidade da demonstração deve informar.

**Documentos necessários:** termos de uso e política de privacidade (CAP-05), previstos para a *release* 1.0.0.

### 5.2 Licenças

- O projeto usa a licença MIT.
- A compatibilidade das licenças das dependências com a MIT deve ser verificada na Fase 3, com verificação automática no CI.
- O FullCalendar deve ser usado apenas com os recursos de licença MIT.

### 5.3 Termos dos fornecedores

O uso da instância de demonstração deve respeitar os termos de uso de cada fornecedor, incluindo a restrição de uso não comercial do plano Hobby da Vercel.

### 5.4 Conclusão legal

Viável, com a publicação dos termos de uso e da política de privacidade na *release* 1.0.0 e o aviso sobre a portabilidade no README.

---

## 6. Viabilidade operacional

| Atividade                          | Forma                                                                             | Esforço                              |
| ---------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------ |
| *Deploy*                           | Automático a partir da *branch* `main`                                            | Nenhum após a configuração           |
| Reinício dos dados da demonstração | *Workflow* agendado no GitHub Actions, diariamente às 03:00 (horário de Brasília) | Nenhum após a configuração           |
| Reativação do agendamento          | Manual, quando o repositório ficar 60 dias sem atividade                          | Poucos minutos, conforme o *runbook* |
| Acompanhamento de cotas e planos   | Consulta mensal aos painéis e às páginas de preços                                | Cerca de 1 h por mês (estimativa)    |
| Backup                             | Não realizado na demonstração: os dados são fictícios e recriados pelo *seed*     | Nenhum                               |

Conclusão: viável. A operação da demonstração é automatizada, com duas tarefas manuais periódicas registradas no *runbook*.

---

## 7. Conclusão geral

**Resultado: viável com ajustes.**

| Dimensão    | Resultado                                                            |
| ----------- | -------------------------------------------------------------------- |
| Técnica     | Viável, com uma prova de conceito na Fase 3                          |
| Econômica   | Viável, com custo zero                                               |
| Cronograma  | Viável com ajustes de escopo e uso do período de 18/01 a 31/01/2027  |
| Legal       | Viável, com termos, política de privacidade e aviso de portabilidade |
| Operacional | Viável                                                               |

### 7.1 Recomendações

| ID   | Recomendação                                                                            | Fase                      |
| ---- | --------------------------------------------------------------------------------------- | ------------------------- |
| R-01 | Usar o período de 18/01 a 31/01/2027 como Sprint 4 e estabilização                      | Fase 1 (plano do projeto) |
| R-02 | Aplicar os ajustes A-01 a A-03 na priorização MoSCoW                                    | Fase 2                    |
| R-03 | Executar a prova de conceito de seleção no calendário, com *timebox* de 6 h             | Fase 3                    |
| R-04 | Fazer o primeiro *deploy* da aplicação mínima na Sprint 1                               | Sprint 1                  |
| R-05 | Não cadastrar meio de pagamento nos fornecedores da demonstração                        | Sprint 1                  |
| R-06 | Registrar as horas trabalhadas por dia no *devlog* e reestimar o escopo após a Sprint 1 | Sprint 1                  |

---

## 8. Fontes

Data de consulta: 28/10/2026.

- [Render: *Deploy* for Free](https://render.com/docs/free)
- [Render.com in Mid-2026: The Plan Change on 1 August](https://jwatte.com/blog/render-com-platform-review.md) (fonte secundária)
- [Neon: Plans](https://neon.com/docs/introduction/plans)
- [Vercel: Hobby Plan](https://vercel.com/docs/plans/hobby)
- [GitHub Docs: Disabling and enabling a *workflow*](https://docs.github.com/en/actions/how-tos/manage-workflow-runs/disable-and-enable-workflows)
