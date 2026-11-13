# Registro de Riscos

| Campo     | Valor              |
| --------- | ------------------ |
| Projeto   | Root Book          |
| Documento | Registro de Riscos |
| Versão    | 0.3                |
| Data      | 12/11/2026         |
| Autor     | Samuel             |
| Status    | Rascunho           |

## Histórico de revisões

| Versão | Data       | Autor  | Descrição                                                                                            |
| ------ | ---------- | ------ | ---------------------------------------------------------------------------------------------------- |
| 0.1    | 12/11/2026 | Samuel | Identificação e análise qualitativa iniciais.                                                        |
| 0.2    | 12/11/2026 | Samuel | Atualização do prazo de entrega do MVP 1 para 31/01/2027 e alinhamento com novo cronograma.          |
| 0.3    | 12/11/2026 | Samuel | Ajuste da disponibilidade para 15 h semanais nas Fases 1 a 4 e 30 h semanais na construção do MVP 1. |

---

## 1. Propósito

Este registro identifica os riscos do MVP 1, avalia sua probabilidade e seu impacto e define a resposta a cada um. Segue os processos de identificação, análise qualitativa e planejamento de respostas aos riscos do PMBOK. É atualizado durante todo o projeto, conforme a seção 6.

## 2. Escalas

### 2.1 Probabilidade

Probabilidade de o risco ocorrer até a entrega do MVP 1 (31/01/2027).

| Nível | Descrição   | Faixa        |
| ----- | ----------- | ------------ |
| 1     | Muito baixa | Menos de 10% |
| 2     | Baixa       | 10% a 30%    |
| 3     | Média       | 30% a 50%    |
| 4     | Alta        | 50% a 70%    |
| 5     | Muito alta  | Mais de 70%  |

### 2.2 Impacto

| Nível | Descrição   | Efeito                                                                                                         |
| ----- | ----------- | -------------------------------------------------------------------------------------------------------------- |
| 1     | Muito baixo | Sem efeito perceptível no escopo ou no prazo                                                                   |
| 2     | Baixo       | Atraso de até 5 h ou ajuste menor                                                                              |
| 3     | Médio       | Atraso de 5 h a 15 h ou adiamento de capacidade *Could*                                                        |
| 4     | Alto        | Atraso de 15 h a 30 h (até uma sprint), adiamento de capacidade *Should* ou demonstração indisponível por dias |
| 5     | Muito alto  | Perda do prazo de 31/01/2027, incidente de segurança ou de privacidade, ou interrupção do projeto              |

### 2.3 Exposição

Exposição = probabilidade × impacto.

| Faixa   | Classificação | Tratamento                                         |
| ------- | ------------- | -------------------------------------------------- |
| 1 a 4   | Baixa         | Monitorar                                          |
| 5 a 9   | Média         | Resposta planejada e revisão por sprint            |
| 10 a 16 | Alta          | Resposta ativa desde o início e revisão por sprint |
| 20 a 25 | Crítica       | Ação imediata e reavaliação do plano               |

## 3. Matriz de exposição

| Impacto \ Probabilidade | 1 Muito baixa | 2 Baixa        | 3 Média                | 4 Alta         | 5 Muito alta |
| ----------------------- | ------------- | -------------- | ---------------------- | -------------- | ------------ |
| **5 Muito alto**        |               | RSK-11, RSK-14 | RSK-13                 |                |              |
| **4 Alto**              |               | RSK-06, RSK-12 | RSK-02, RSK-04         | RSK-01         |              |
| **3 Médio**             |               | RSK-07, RSK-16 | RSK-05, RSK-15, RSK-17 | RSK-03, RSK-08 |              |
| **2 Baixo**             |               |                | RSK-09                 | RSK-10         |              |
| **1 Muito baixo**       |               |                |                        |                |              |

## 4. Resumo

Ordenado por exposição.

| ID     | Categoria                 | Evento                                                                        | P   | I   | Exposição | Classificação | Estratégia                   | Status |
| ------ | ------------------------- | ----------------------------------------------------------------------------- | --- | --- | --------- | ------------- | ---------------------------- | ------ |
| RSK-01 | Cronograma e escopo       | Escopo do MVP 1 excede a capacidade das sprints                               | 4   | 4   | 16        | Alta          | Mitigar                      | Aberto |
| RSK-13 | Segurança e privacidade   | Usuário acessa dados de outro usuário                                         | 3   | 5   | 15        | Alta          | Mitigar                      | Aberto |
| RSK-02 | Técnica                   | Seleção no calendário e reserva de blocos consomem mais tempo que o estimado  | 3   | 4   | 12        | Alta          | Mitigar                      | Aberto |
| RSK-03 | Cronograma e escopo       | Atividades acadêmicas e feriados reduzem as horas disponíveis                 | 4   | 3   | 12        | Alta          | Mitigar                      | Aberto |
| RSK-04 | Cronograma e escopo       | Documentação das Fases 1 a 4 excede 120 h                                     | 3   | 4   | 12        | Alta          | Mitigar                      | Aberto |
| RSK-08 | Instância de demonstração | Visitante interpreta a hibernação da demonstração como falha                  | 4   | 3   | 12        | Alta          | Mitigar                      | Aberto |
| RSK-11 | Segurança e privacidade   | Segredo de conexão é exposto                                                  | 2   | 5   | 10        | Alta          | Evitar                       | Aberto |
| RSK-14 | Processo                  | Projeto é interrompido antes da 1.0.0                                         | 2   | 5   | 10        | Alta          | Mitigar                      | Aberto |
| RSK-05 | Processo                  | Requisitos ou usabilidade inadequados por ausência de validação por terceiros | 3   | 3   | 9         | Média         | Mitigar e aceitar o residual | Aberto |
| RSK-15 | Segurança e privacidade   | Dependência ou migração causa falha ou vulnerabilidade                        | 3   | 3   | 9         | Média         | Mitigar                      | Aberto |
| RSK-17 | Cronograma e escopo       | MVP 1 fica reduzido demais para demonstrar o valor do produto                 | 3   | 3   | 9         | Média         | Mitigar                      | Aberto |
| RSK-06 | Instância de demonstração | Plano gratuito de um fornecedor é alterado ou encerrado                       | 2   | 4   | 8         | Média         | Mitigar                      | Aberto |
| RSK-10 | Instância de demonstração | Visitante altera os dados compartilhados da conta de exemplo                  | 4   | 2   | 8         | Média         | Mitigar                      | Aberto |
| RSK-12 | Segurança e privacidade   | Instância de demonstração coleta dados pessoais de visitantes                 | 2   | 4   | 8         | Média         | Evitar                       | Aberto |
| RSK-07 | Instância de demonstração | Cota mensal de um plano gratuito se esgota                                    | 2   | 3   | 6         | Média         | Mitigar                      | Aberto |
| RSK-09 | Instância de demonstração | Agendamento de reinício é desativado pelo GitHub                              | 3   | 2   | 6         | Média         | Mitigar                      | Aberto |
| RSK-16 | Processo                  | Trabalho local é perdido                                                      | 2   | 3   | 6         | Média         | Mitigar                      | Aberto |

## 5. Detalhamento

### 5.1 Causa, evento e efeito

| ID     | Causa                                                                                                       | Evento                                                                                       | Efeito                                                      |
| ------ | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| RSK-01 | Estimativa do MVP 1 (136 h) acima da capacidade planejável (126 h)                                          | Escopo excede a capacidade das sprints                                                       | Capacidades não entregues ou atraso em relação a 31/01/2027 |
| RSK-02 | Interação de seleção no calendário e paleta de comandos dependem de biblioteca ainda não testada no projeto | Implementação consome mais tempo que o estimado                                              | Atraso no MOD-05 e no MOD-08                                |
| RSK-03 | Provas e trabalhos de fim de semestre; feriados de 20/11, 25/12 e 01/01                                     | Horas disponíveis abaixo das planejadas (15 h por semana nas Fases 1 a 4 e 30 h nas sprints) | Atraso nas fases ou nas sprints                             |
| RSK-04 | Detalhamento excessivo dos documentos                                                                       | Documentação excede 120 h                                                                    | Início da construção adiado                                 |
| RSK-05 | Projeto sem participação de terceiros                                                                       | Requisitos ou usabilidade inadequados                                                        | Retrabalho e menor valor para o usuário                     |
| RSK-06 | Fornecedores alteram os planos com frequência                                                               | Plano gratuito alterado ou encerrado                                                         | Demonstração indisponível ou com custo                      |
| RSK-07 | Uso acima do previsto ou *keep-alive* mal configurado                                                       | Cota mensal esgotada                                                                         | Demonstração suspensa até o mês seguinte                    |
| RSK-08 | API e banco hibernam após inatividade                                                                       | Primeira resposta leva cerca de 1 min                                                        | Visitante abandona a avaliação                              |
| RSK-09 | GitHub desativa agendamentos após 60 dias sem atividade em repositórios públicos                            | Reinício diário deixa de ser executado                                                       | Dados da demonstração desatualizados ou inconsistentes      |
| RSK-10 | Conta de exemplo compartilhada entre visitantes                                                             | Visitante altera ou exclui dados                                                             | Demonstração incoerente até o próximo reinício              |
| RSK-11 | Segredos manipulados em arquivos locais, CI e painéis                                                       | Segredo exposto no repositório ou em logs                                                    | Acesso indevido ao banco da demonstração                    |
| RSK-12 | Funcionalidade de cadastro ou formulário ativo na demonstração                                              | Coleta de dados pessoais de visitantes                                                       | Obrigações da LGPD e transferência internacional de dados   |
| RSK-13 | Consulta sem filtro por usuário                                                                             | Acesso a dados de outro usuário                                                              | Incidente de segurança e de privacidade                     |
| RSK-14 | Esgotamento, falta de tempo ou mudança de prioridades                                                       | Interrupção do projeto                                                                       | Portfólio sem produto demonstrável                          |
| RSK-15 | Atualização de dependência ou migração incompatível                                                         | Falha no deploy ou vulnerabilidade                                                           | Demonstração indisponível ou exposta                        |
| RSK-16 | Falha ou perda do computador de desenvolvimento                                                             | Perda de trabalho não enviado ao repositório                                                 | Retrabalho                                                  |
| RSK-17 | Corte de escopo para caber no prazo                                                                         | MVP 1 sem a reserva de tempo para tarefas, que diferencia o produto                          | Demonstração que não mostra o valor do produto              |

### 5.2 Resposta, gatilho e responsável

| ID     | Estratégia e ações de resposta                                                                                                                                           | Gatilho                                                                                 | Responsável            |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- | ---------------------- |
| RSK-01 | Mitigar: priorização MoSCoW com limite de 126 h para *Must*; candidatas a adiamento definidas no estudo de viabilidade; acompanhamento da velocidade por sprint          | Velocidade abaixo de 85% do planejado ao fim de qualquer sprint                         | Gerente de projeto     |
| RSK-02 | Mitigar: prova de conceito na Fase 3 com timebox de 6 h; uso de biblioteca de calendário com seleção nativa                                                              | Prova de conceito não concluída no timebox                                              | Arquiteto              |
| RSK-03 | Mitigar: timebox por fase e por sprint; registro diário de horas; replanejamento semanal                                                                                 | Uma semana abaixo de 80% das horas planejadas (12 h nas Fases 1 a 4 e 24 h nas sprints) | Gerente de projeto     |
| RSK-04 | Mitigar: timebox de 30 h por fase; reduzir o detalhamento em vez de adiar a fase seguinte                                                                                | Fase ultrapassa 36 h (120% do timebox)                                                  | Gerente de projeto     |
| RSK-05 | Mitigar: análise de concorrentes, prototipação com percurso cognitivo, avaliação heurística e dogfooding. Aceitar o residual e declará-lo no README.                     | Problemas de severidade 3 ou 4 na avaliação heurística                                  | Analista de requisitos |
| RSK-06 | Mitigar: conteinerização para migrar a demonstração; alternativas registradas no ADR de hospedagem; consulta mensal às páginas de preços                                 | Anúncio de mudança de plano por um fornecedor                                           | Operações              |
| RSK-07 | Mitigar: banco sem *keep-alive*; no máximo um serviço do Render sempre ativo; consulta mensal aos painéis de uso                                                         | Consumo acima de 80% de uma cota                                                        | Operações              |
| RSK-08 | Mitigar: aviso de inicialização (CAP-54); aviso no README; *keep-alive* opcional da API                                                                                  | Tempo de resposta inicial acima de 10 s em medição                                      | Desenvolvedor          |
| RSK-09 | Mitigar: procedimento de reativação no runbook; execução manual pelo `workflow_dispatch`                                                                                 | Ausência de execução do workflow por mais de 2 dias                                     | Operações              |
| RSK-10 | Mitigar: bloqueios do modo demonstração (CAP-54); reinício diário dos dados                                                                                              | Dados da conta de exemplo diferentes do seed                                            | Operações              |
| RSK-11 | Evitar: segredos apenas em variáveis de ambiente e em segredos do GitHub; `.env` fora do controle de versão; varredura de segredos; rotação imediata em caso de suspeita | Alerta da varredura de segredos                                                         | Operações              |
| RSK-12 | Evitar: cadastro desativado no modo demonstração; logs sem dados pessoais (CAP-53); política de privacidade da demonstração                                              | Qualquer funcionalidade da demonstração que receba dados pessoais                       | Analista de requisitos |
| RSK-13 | Mitigar: filtro por usuário centralizado na API; testes automatizados de acesso indevido entre dois usuários; modelagem de ameaças STRIDE na Fase 3                      | Falha em teste de autorização                                                           | Arquiteto              |
| RSK-14 | Mitigar: uma release por sprint, publicada na demonstração; limite de 30 h semanais                                                                                      | Duas sprints consecutivas sem release                                                   | Patrocinador           |
| RSK-15 | Mitigar: versões fixadas no lockfile; Dependabot; migrações compatíveis com a versão anterior; procedimento de rollback no runbook                                       | Falha no deploy ou alerta do Dependabot de severidade alta                              | Operações              |
| RSK-16 | Mitigar: envio diário do trabalho ao repositório remoto, mesmo em branches não concluídas                                                                                | Trabalho local não enviado há mais de 1 dia                                             | Desenvolvedor          |
| RSK-17 | Mitigar: manter no MVP 1 a reserva de um horário livre para uma tarefa (CAP-26, CAP-27 e CAP-31) como *Must*; cortar primeiro as capacidades de suporte                  | Proposta de adiar CAP-26, CAP-27 ou CAP-31                                              | Patrocinador           |

Todas as responsabilidades são do autor, no papel indicado.

## 6. Monitoramento

- O registro é revisado em cada sprint review e em cada gate de fase.
- Os gatilhos são verificados na revisão. Quando um gatilho é atingido, a resposta é executada e o status passa para "Em tratamento" ou "Ocorrido".
- Novos riscos são registrados como issues com o label `risco` e incorporados a este documento na revisão seguinte.
- Status possíveis: Aberto, Em tratamento, Ocorrido, Encerrado.
