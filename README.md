# Root Book

Software web de planejamento pessoal que reúne rotina fixa, tarefas e blocos de tempo no mesmo calendário. Projeto de portfólio com o ciclo de desenvolvimento documentado.

| Item              | Valor                                                |
| ----------------- | ---------------------------------------------------- |
| Status do projeto | Em concepção ([Fase 1](docs/01-concepcao/README.md)) |
| Previsão do MVP 1 | 31/01/2027 (release 1.0.0)                           |
| Licença           | [MIT](LICENSE)                                       |

---

## 1. Sobre o projeto

Pessoas com rotina variada costumam registrar compromissos em um calendário e tarefas em uma lista separada, sem reservar no calendário o tempo necessário para executar as tarefas. O Root Book reúne eventos, tarefas e blocos de tempo no mesmo calendário e permite reservar tempo para uma tarefa diretamente em um horário livre. A descrição completa do problema e do posicionamento está na [Visão do Produto](docs/01-concepcao/01-visao-do-produto-mvp1.md#2-posicionamento).

O projeto é desenvolvido individualmente, com o ciclo de vida completo documentado: concepção, requisitos, arquitetura, planejamento, desenvolvimento, qualidade, implantação, operação e encerramento.

---

## 2. Funcionalidades previstas no MVP 1

Capacidades candidatas da [Visão do Produto](docs/01-concepcao/01-visao-do-produto-mvp1.md#6-capacidades), sujeitas à priorização MoSCoW da Fase 2.

| Módulo                    | Funcionalidade                                                                                                |
| ------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Conta e acesso            | Cadastro com e-mail e senha, entrada e saída da conta; cada usuário acessa apenas os próprios dados           |
| Privacidade               | Consentimento com os termos de uso e a política de privacidade no cadastro; exclusão da conta e dos dados     |
| Organização               | Criação, renomeação e exclusão de Espaços                                                                     |
| Calendário                | Visão semanal com eventos com horário e blocos de tempo, diferenciados visualmente                            |
| Tarefas                   | Criação, edição e exclusão de tarefas, com data planejada, prazo e duração estimada opcionais, e status       |
| Planejamento              | Seleção de um intervalo livre no calendário e reserva desse intervalo para uma tarefa pela paleta de comandos |
| Fuso horário              | Horários armazenados em UTC e exibidos no fuso do usuário                                                     |
| Instância de demonstração | Modo demonstração com conta de exemplo e reinício diário dos dados                                            |

---

## 3. Demonstração

| Item                            | Valor         |
| ------------------------------- | ------------- |
| *Link*                          | `[A DEFINIR]` |
| Credenciais da conta de exemplo | `[A DEFINIR]` |

Avisos de uso da instância de demonstração:

- Os dados são fictícios e reiniciados diariamente.
- O cadastro, a recuperação de senha, a troca de senha e a exclusão da conta estão desativados.
- A instância usa planos gratuitos que hibernam após um período sem acesso; a primeira resposta pode levar cerca de 1 minuto.

---

## 4. Como executar

O projeto poderá ser executado com Docker Compose, localmente ou em um servidor, com `DEMO_MODE=false`. As instruções de execução serão publicadas na release 1.0.0.

---

## 5. Stack

| Componente     | Uso no projeto                           |
| -------------- | ---------------------------------------- |
| TypeScript     | Linguagem de todo o código               |
| Next.js        | Front-end                                |
| NestJS         | API                                      |
| PostgreSQL     | Banco de dados                           |
| Prisma ORM     | Acesso a dados e migrações               |
| Zod            | Validação                                |
| JWT            | Autenticação                             |
| SWC            | Compilação                               |
| Vitest         | Testes unitários e de integração         |
| Testcontainers | Testes de integração com PostgreSQL real |
| Docker Compose | Execução do projeto                      |

---

## 6. Documentação

| Fase                        | Pasta                                                | Status       |
| --------------------------- | ---------------------------------------------------- | ------------ |
| 1. Concepção                | [`docs/01-concepcao`](docs/01-concepcao/README.md)   | Em andamento |
| 2. Requisitos               | [`docs/02-requisitos`](docs/02-requisitos)           | Pendente     |
| 3. Arquitetura              | [`docs/03-arquitetura`](docs/03-arquitetura)         | Pendente     |
| 4. Planejamento da execução | [`docs/04-planejamento`](docs/04-planejamento)       | Pendente     |
| 5. Desenvolvimento          | [`docs/05-desenvolvimento`](docs/05-desenvolvimento) | Pendente     |
| 6. Qualidade e testes       | [`docs/06-qualidade`](docs/06-qualidade)             | Pendente     |
| 7. Implantação              | [`docs/07-implantacao`](docs/07-implantacao)         | Pendente     |
| 8. Operação                 | [`docs/08-operacao`](docs/08-operacao)               | Pendente     |
| 9. Encerramento             | [`docs/09-encerramento`](docs/09-encerramento)       | Pendente     |

Procedimentos que valem para todas as fases:

| Procedimento                                                           | Conteúdo                                                |
| ---------------------------------------------------------------------- | ------------------------------------------------------- |
| [Padrão de documentos](docs/processo/01-padrao-de-documentos.md)       | Estrutura, formato, identificadores e regras de escrita |
| [Aprovação de documentos](docs/processo/02-aprovacao-de-documentos.md) | Ciclo de vida de um documento, revisão e *gate* de fase |

---

## 7. Processo

- **Ciclo de vida:** iterativo e incremental, organizado nas fases do RUP. As Fases 1 a 4 produzem a documentação; a construção ocorre em *sprints* de uma semana, com uma release por *sprint*. O detalhamento está no [plano do projeto](docs/01-concepcao/06-plano-do-projeto.md).
- **Documentação versionada:** os documentos ficam no repositório, com histórico de revisões. Cada fase termina em um *gate* que registra a decisão e cria uma tag de *baseline*.
- **Revisões:** cada documento é revisado com o checklist do [procedimento de aprovação](docs/processo/02-aprovacao-de-documentos.md), em dia diferente daquele em que foi produzido.
- **Limitação:** o projeto não tem participação de terceiros. O autor exerce todos os papéis, e os requisitos e a usabilidade são validados por análise de concorrentes, prototipação, avaliação heurística e uso do sistema pelo próprio autor, sem validação por usuários externos.

---

## 8. Autor

Samuel, estudante de Engenharia de Software na Universidade de Brasília (UnB), Faculdade de Ciências e Tecnologias em Engenharia (FCTE).

---

## 9. Licença

Distribuído sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE).
