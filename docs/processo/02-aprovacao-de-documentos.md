# Procedimento de aprovação de documentos

| Campo     | Valor                                   |
| --------- | --------------------------------------- |
| Projeto   | Root Book                               |
| Documento | Procedimento de aprovação de documentos |
| Versão    | 0.1                                     |
| Data      | 03/11/2026                              |
| Autor     | Samuel                                  |
| Status    | Rascunho                                |

## Histórico de revisões

| Versão | Data       | Autor  | Descrição       |
| ------ | ---------- | ------ | --------------- |
| 0.1    | 03/11/2026 | Samuel | Versão inicial. |

---

## 1. Propósito

Este procedimento define os passos para revisar e aprovar os documentos de uma fase e vale para todas as fases. Nos exemplos, `N` é o número da fase, `<issue>` é o número da *issue* correspondente e `<tag>` é a *tag* da *baseline* definida no plano do projeto (*link* `[A DEFINIR]`).

---

## 2. Ciclo de vida de um documento

| Status                 | Versão | Significado                                           |
| ---------------------- | ------ | ----------------------------------------------------- |
| Rascunho               | 0.1    | Escrito e ainda não revisado                          |
| Em revisão             | 0.x    | Revisão pelo autor em andamento                       |
| Aguardando aprovação   | 0.x    | Revisado e à espera do *gate* da fase                 |
| Aprovado               | 1.0    | Aprovado no *gate* da fase                            |
| Congelado (*baseline*) | 1.0    | Aprovado e sem novas edições (somente a Visão do produto) |

---

## 3. Parte A: revisão de cada documento

Repetir para cada documento da fase. A revisão é feita em dia diferente daquele em que o documento foi escrito.

### 3.1 Antes de revisar

- [ ] Alterar o status do cabeçalho para "Em revisão".

### 3.2 *Checklist* de revisão

**Conteúdo**

- [ ] O documento cumpre a finalidade descrita na seção de propósito.
- [ ] Nenhum dado foi inventado; todo valor desconhecido aparece como `[A DEFINIR]`.
- [ ] Cada `[A DEFINIR]` restante está registrado como pendência, com prazo, no documento do *gate* da fase.
- [ ] Estimativas e recomendações estão identificadas como tais.

**Consistência**

- [ ] Os identificadores citados existem no documento de origem e têm o mesmo significado em todos os documentos.
- [ ] Datas, horários e números conferem com os demais documentos.

**Forma**

- [ ] O documento segue o [padrão de documentos](./01-padrao-de-documentos.md).
- [ ] Os *links* internos abrem a seção correta no GitHub.
- [ ] Os diagramas Mermaid são renderizados corretamente no GitHub.
- [ ] O texto segue as regras de escrita do padrão.
- [ ] Não há erros de ortografia nem de concordância.

### 3.3 Registro da revisão

- [ ] Fazer as correções.
- [ ] Incrementar a versão (de 0.1 para 0.2, por exemplo) e atualizar a data do cabeçalho.
- [ ] Incluir no histórico de revisões uma linha que descreva as correções. Se não houver correções, registrar "Revisado sem alterações" e manter a versão.
- [ ] Alterar o status para "Aguardando aprovação".
- [ ] Fazer o *commit*, por exemplo, `tipo(escopo): descrição`.

---

## 4. Parte B: *gate* da fase

Executar quando todos os documentos da fase estiverem com status "Aguardando aprovação".

### 4.1 Preparação

- [ ] Criar a *branch* a partir da `main` atualizada:

  ```bash
  git checkout main
  git pull
  git checkout -b docs/<issue>-gate-fase-N
  ```

### 4.2 Documento do *gate*

- [ ] Marcar com `[x]` cada critério de saída atendido e conferir a evidência indicada.
- [ ] Revisar a tabela de pendências e confirmar que cada item tem descrição e prazo.
- [ ] Marcar a decisão: aprovar, aprovar com ressalvas ou reprovar.
- [ ] Preencher a data e as ressalvas, se houver.

Em caso de reprovação, os documentos voltam à Parte A e os passos seguintes não são executados.

### 4.3 Atualização dos documentos aprovados

Para cada documento da fase:

- [ ] Versão: `1.0`.
- [ ] Data: data da aprovação.
- [ ] Status: `Aprovado`. A Visão do produto recebe `Congelado (baseline)`.
- [ ] Histórico: linha `1.0 | DD/MM/AAAA | Samuel | Aprovado no gate da Fase N.`

### 4.4 Documentos que dependem da aprovação

- [ ] Termo de abertura (somente na Fase 1): preencher a decisão e a data na seção de aprovação.
- [ ] README da pasta da fase: atualizar as versões e os status na tabela de documentos e marcar a fase como "Concluída".
- [ ] README da raiz: marcar a fase como "Concluída" na tabela de documentação e atualizar o status do projeto.

### 4.5 Registro no repositório

- [ ] Fazer o *commit* e enviar a *branch*:

  ```bash
  git add docs/ README.md
  git commit -m "docs: aprovar documentos no gate da fase N"
  git push -u origin docs/<issue>-gate-fase-N
  ```

- [ ] Abrir o *pull request* (PR) com o título "Gate da Fase N" e incluir na descrição `Closes #<issue>` e o *link* para o documento do *gate*.
- [ ] Revisar o PR e fazer o *merge* na `main`.
- [ ] Criar e enviar a *tag* anotada da *baseline*:

  ```bash
  git checkout main
  git pull
  git tag -a <tag> -m "Baseline da Fase N"
  git push origin <tag>
  ```

- [ ] Mover as *issues* da fase para "Concluído" no GitHub Projects.

### 4.6 Encerramento

- [ ] Registrar no *devlog* a data do *gate* e o total de horas gastas na fase.
- [ ] Iniciar a fase seguinte.

---

## 5. Alterações após a aprovação

| Tipo de documento | Exemplos                                                         | Como alterar                                                                                                         |
| ----------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Congelado         | Visão do produto                                                 | Sem alteração; as mudanças são registradas na especificação de requisitos de software (SRS)                          |
| *Baseline*        | SRS, ADRs aceitos, plano de *releases*                           | Somente por *issue* com o *label* `change-request`, conforme o processo de gestão de mudanças definido no plano do projeto |
| Vivo              | Registro de riscos, registro de *stakeholders*, plano do projeto | Alteração direta, com incremento da versão (1.1, 1.2 e assim por diante) e linha no histórico, sem novo *gate*       |
