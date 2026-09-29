# Apply Tracker - Casos de Uso

## 1. Visão geral

O Apply Tracker permite que usuários registrem, acompanhem e analisem suas candidaturas para vagas de emprego.

Os casos de uso representam as principais interações entre o usuário e o sistema, descrevendo o que o sistema deve permitir realizar sem definir detalhes de implementação.

---

## 2. Atores

### U01 - Usuário

Pessoa que utiliza o sistema para cadastrar, acompanhar e analisar suas candidaturas.

---

# 3. Casos de uso

## UC01 - Criar conta

**Ator:** U01 - Usuário

**Objetivo:** Permitir que uma pessoa crie uma conta no sistema.

**Requisitos relacionados:** RN05, RN06, RN07, RN08, RN42, RN43.

## UC02 - Autenticar usuário

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário acesse sua conta.

**Requisitos relacionados:** RN10, RN12.

## UC03 - Recuperar conta

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário recupere o acesso à conta utilizando seu código de recuperação.

**Requisitos relacionados:** RN07, RN08, RN09.

## UC04 - Alterar e-mail da conta

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário altere o e-mail associado à conta.

**Requisitos relacionados:** RN05, RN06, RN08, RN09.

# 4. Gerenciamento de currículos

## UC05 - Cadastrar currículo

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário cadastre um currículo para utilizá-lo em candidaturas.

**Requisitos relacionados:** RF13.

## UC06 - Gerenciar currículos

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário visualize, edite e exclua seus currículos cadastrados.

**Requisitos relacionados:** RF13, RN12.

# 5. Gerenciamento de candidaturas

## UC07 - Criar candidatura

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário registre uma nova candidatura.

**Requisitos relacionados:** RF05, RF13, RN11, RN13, RN14, RN15, RN16, RN17, RN18, RN19, RN20, RN21, RN22, RN28, RN29, RN30.

## UC08 - Visualizar candidaturas

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário visualize suas candidaturas.

**Requisitos relacionados:** RF01, RF02, RN12, RN35.

## UC09 - Visualizar candidatura

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário visualize todos os dados de uma candidatura específica.

**Requisitos relacionados:** RF02, RF12, RN12, RN38.

## UC10 - Editar candidatura

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário altere os dados de uma candidatura.

**Requisitos relacionados:** RF06, RN12, RN13, RN14, RN15, RN16, RN17, RN18, RN19, RN20, RN21, RN29, RN30.

# 6. Gerenciamento de etapas

## UC11 - Alterar estado de uma etapa

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário registre o resultado de uma etapa do processo seletivo.

**Requisitos relacionados:** RF02, RF12, RN23, RN24, RN25, RN26, RN27, RN38, RN39.

## UC12 - Visualizar histórico de etapas

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário acompanhe o histórico de uma candidatura.

**Requisitos relacionados:** RF12, RN38, RN39.

# 7. Filtros e dashboard

## UC13 - Filtrar candidaturas

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário encontre candidaturas utilizando filtros.

**Requisitos relacionados:** RF04.

## UC14 - Visualizar indicadores das candidaturas

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário acompanhe a quantidade de candidaturas em cada etapa.

**Requisitos relacionados:** RF03.

## UC15 - Identificar gargalos

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário identifique pontos de dificuldade durante seus processos seletivos.

**Requisitos relacionados:** RF10, RN40, RN41.

## UC16 - Visualizar recomendações

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário encontre materiais relacionados aos seus déficits identificados.

**Requisitos relacionados:** RF11.

# 8. Lixeira

## UC17 - Excluir candidatura

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário remova uma candidatura da listagem normal sem excluí-la imediatamente.

**Requisitos relacionados:** RF07, RF08, RF09, RN12, RN31, RN35.

## UC18 - Visualizar lixeira

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário visualize suas candidaturas excluídas.

**Requisitos relacionados:** RN31, RN32.

## UC19 - Restaurar candidatura

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário restaure uma candidatura antes da exclusão permanente.

**Requisitos relacionados:** RF08, RN31, RN32, RN36.

## UC20 - Excluir candidatura permanentemente

**Ator:** U01 - Usuário

**Objetivo:** Permitir que o usuário exclua definitivamente uma candidatura da lixeira.

**Requisitos relacionados:** RF08, RN33.

## UC21 - Excluir candidaturas expiradas

**Ator:** Sistema

**Objetivo:** Excluir permanentemente candidaturas que permaneceram na lixeira por mais de 15 dias.

**Requisitos relacionados:** RF09, RN31, RN34.

# 9. Tratamento de erros e segurança

## UC22 - Validar operação

**Ator:** U01 - Usuário

**Objetivo:** Garantir que operações realizadas pelo usuário estejam de acordo com as regras do sistema.

**Requisitos relacionados:** RN01, RN02, RN12, RN42, RN43.

# 10. Resumo dos casos de uso

| ID   | Caso de uso                             | Ator    |
| ---- | --------------------------------------- | ------- |
| UC01 | Criar conta                             | Usuário |
| UC02 | Autenticar usuário                      | Usuário |
| UC03 | Recuperar conta                         | Usuário |
| UC04 | Alterar e-mail da conta                 | Usuário |
| UC05 | Cadastrar currículo                     | Usuário |
| UC06 | Gerenciar currículos                    | Usuário |
| UC07 | Criar candidatura                       | Usuário |
| UC08 | Visualizar candidaturas                 | Usuário |
| UC09 | Visualizar candidatura                  | Usuário |
| UC10 | Editar candidatura                      | Usuário |
| UC11 | Alterar estado de uma etapa             | Usuário |
| UC12 | Visualizar histórico de etapas          | Usuário |
| UC13 | Filtrar candidaturas                    | Usuário |
| UC14 | Visualizar indicadores das candidaturas | Usuário |
| UC15 | Identificar gargalos                    | Usuário |
| UC16 | Visualizar recomendações                | Usuário |
| UC17 | Excluir candidatura                     | Usuário |
| UC18 | Visualizar lixeira                      | Usuário |
| UC19 | Restaurar candidatura                   | Usuário |
| UC20 | Excluir candidatura permanentemente     | Usuário |
| UC21 | Excluir candidaturas expiradas          | Sistema |
| UC22 | Validar operação                        | Usuário |
