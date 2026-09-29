# Apply Tracker - Modelagem de Domínio

## 1. Visão geral

A modelagem de domínio representa os principais conceitos do negócio e seus relacionamentos dentro do Apply Tracker.

O domínio é centrado no acompanhamento das candidaturas e na evolução do usuário durante os processos seletivos.

---

# 2. Entidades

## User

Representa o usuário do sistema.

**Principais atributos:**

* id
* email
* password
* recoveryCode
* lastLoginAt

**Relacionamentos:**

* Possui vários currículos.
* Possui várias candidaturas.

---

## Application

Representa uma candidatura realizada pelo usuário.

**Principais atributos:**

* id
* userId
* companyName
* jobTitle
* jobDescription
* companyPhilosophy
* jobUrl
* applicationDate
* applicationMethod
* resumeId
* referred
* createdAt
* updatedAt
* deletedAt

**Relacionamentos:**

* Pertence a um usuário.
* Pode utilizar um currículo.
* Possui uma ou mais etapas.
* Possui uma ou mais habilidades.
* Possui histórico de alterações.

A `Application` é a entidade central do domínio.

---

## ApplicationStage

Representa uma etapa de uma candidatura.

**Principais atributos:**

* id
* applicationId
* stageType
* position
* status
* rejectionReason
* resultReason
* completedAt

**Relacionamentos:**

* Pertence a uma candidatura.
* Possui um tipo de etapa.
* Pode possuir um motivo de reprovação.
* Pode possuir um motivo de aprovação.

---

## Resume

Representa um currículo cadastrado pelo usuário.

**Principais atributos:**

* id
* userId
* name

**Relacionamentos:**

* Pertence a um usuário.
* Pode ser associado a candidaturas.

---

## Skill

Representa uma habilidade exigida por uma vaga.

**Principais atributos:**

* id
* name

**Relacionamentos:**

* Pode estar associada a várias candidaturas.

---

## ApplicationHistory

Representa uma alteração realizada no estado de uma etapa.

**Principais atributos:**

* id
* applicationId
* stageId
* previousStatus
* newStatus
* reason
* createdAt

**Relacionamentos:**

* Pertence a uma candidatura.
* Está relacionada a uma etapa.

---

# 3. Objetos de valor

## Email

Representa um endereço de e-mail válido.

Responsável por garantir que o valor utilizado como e-mail esteja em formato válido.

---

## Url

Representa uma URL válida utilizada pela candidatura.

---

## Salary

Representa uma pretensão salarial, caso informada.

---

# 4. Enums

## ApplicationStageStatus

Estados possíveis de uma etapa:

* PENDING
* PASSED
* FAILED

---

## ApplicationMethod

Representa o meio utilizado para realizar a candidatura.

Exemplos:

* LinkedIn
* Gupy
* E-mail
* Site da empresa
* Indicação
* Outro

---

## StageType

Tipos de etapas predefinidas:

* Triagem
* Entrevista RH
* Entrevista técnica
* Teste técnico
* Entrevista gestor
* Entrevista final
* Proposta

---

# 5. Relacionamentos principais

```text
User
 ├── 1:N ── Resume
 └── 1:N ── Application
                 ├── 1:N ── ApplicationStage
                 ├── N:N ── Skill
                 └── 1:N ── ApplicationHistory
```

---

# 6. Agregado principal

## Application

`Application` é o agregado principal do domínio.

Uma candidatura controla:

* suas etapas;
* seus estados;
* seu histórico;
* suas habilidades;
* suas informações relacionadas ao processo seletivo.

As alterações relevantes da candidatura devem respeitar as regras do domínio.

---

# 7. Principais invariantes do domínio

* Uma candidatura pertence a apenas um usuário.
* Um usuário só pode acessar suas próprias candidaturas.
* Uma candidatura deve possuir pelo menos uma etapa.
* As etapas possuem uma ordem definida.
* Uma etapa inicia como `PENDING`.
* Uma etapa `PENDING` pode se tornar `PASSED` ou `FAILED`.
* Uma etapa concluída não pode mudar diretamente para outro resultado.
* Uma etapa reprovada deve possuir motivo quando essa informação for conhecida.
* O histórico deve preservar as alterações realizadas nas etapas.
* Uma candidatura excluída não aparece nas listagens normais.
* Uma candidatura pode ser restaurada durante o período de 15 dias.
* Após 15 dias na lixeira, a candidatura deve ser excluída permanentemente.
* O sistema não deve inferir um motivo de reprovação que não tenha sido informado pelo usuário.

---

# 8. Conceitos que não fazem parte do domínio

Os seguintes conceitos pertencem a outras camadas do sistema e não são entidades de domínio:

* Controller
* Repository
* Service
* API Request
* API Response
* Dashboard
* Authentication Service
* Recommendation Service
* Database
* HTTP Request
* HTTP Response

Esses componentes podem manipular o domínio, mas não representam conceitos centrais do negócio.