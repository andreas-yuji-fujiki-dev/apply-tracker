# Apply Tracker - Sistema de rastreamento de candidaturas para vagas de emprego

## Objetivo

Tornar fácil a visualização:

* Das empresas em que você se candidatou
* Das filosofias das empresas em que você se candidatou
* De que etapa você está em cada candidatura e quantas etapas são
* De qual currículo você mandou para cada vaga
* Do meio pelo qual você se candidatou em cada vaga
* De se houve indicação
* De quais gargalos estão acontecendo em quais etapas
* De onde você foi aprovado e o motivo
* De onde você foi reprovado e o motivo

## Usuários do sistema

* U01 - Pessoas que querem acompanhar suas candidaturas e identificar os próprios déficits e pontos a melhorar.

## Problemas encontrados

* P01 - Pessoas fazem muitas candidaturas para muitas vagas e não conseguem se organizar

* P02 - Pessoas se esquecem de quais candidaturas fizeram para cada empresa, da cultura/valores, pretensão salarial, benefícios, stack, qual currículo enviaram para cada empresa, nem em que data fizeram suas candidaturas

* P03 - As pessoas não conseguem identificar muitos dos próprios gargalos de desempenho para cada área, por exemplo: currículo, entrevista, teste técnico

## Requisitos funcionais

* RF01 - Listagem de candidaturas feitas em forma de card.

* RF02 - Card deve ter: dados sobre a publicação da vaga, data da candidatura, qual currículo foi enviado, método de candidatura (LinkedIn, Gupy, e-mail, etc.), link da vaga, etapas do processo podendo clicar em "passei", as habilidades exigidas pela vaga e um botão "fui reprovado" com um select de motivo.

* RF03 - Na listagem, mostrar contagem de candidaturas por etapa (ex: 30 currículos enviados, 20 entrevistas com RH, 13 entrevistas técnicas, 10 propostas).

* RF04 - Filtragem de candidaturas por etapa, data ou mês.

* RF05 - Criação de card podendo informar os dados descritos acima e personalizar as etapas do processo baseado em opções predefinidas selecionáveis, porque cada empresa pode ter um processo diferente, mas as etapas que podem existir ou não seguem um padrão previsível.

* RF06 - Edição de cards de candidatura.

* RF07 - Deleção de cards de candidatura.

* RF08 - Soft delete e "esvaziar lixeira" (esvaziar lixeira = apagar permanentemente).

* RF09 - Cards na lixeira são excluídos permanentemente após 15 dias.

* RF10 - Dashboard indicando gargalos, se houver, informativo indicando quantas vezes o usuário não avançou em um processo por conta de currículo, entrevista ou teste técnico, ou outros motivos.

* RF11 - Recomendações de materiais para se tornar mais proficiente em cada uma das áreas de déficit, como indicações de livros sobre entrevistas, sites para treinar testes técnicos, vídeos, etc.

* RF12 - Visualização do histórico de etapas de cada candidatura.

* RF13 - Cadastro e gerenciamento dos currículos utilizados nas candidaturas.

## Requisitos não funcionais

* RNF01 - Autenticação de usuários.

* RNF02 - A aplicação deve funcionar em dispositivos móveis.

* RNF03 - A disponibilidade da aplicação deve ser de 99,9% do tempo.

* RNF04 - Os dados não podem se perder ao trocar de máquina ou recarregar a página.

* RNF05 - As informações de cada usuário têm que ser protegidas.

* RNF06 - O servidor deve validar e autorizar todas as operações, não confiando em dados, estados ou eventos fornecidos pelo cliente.

* RNF07 - Backups dos dados devem ser realizados periodicamente.

* RNF08 - A comunicação entre frontend e backend deve ser realizada de forma segura.

## Regras de negócio

* RN01 - A API deve ter sistema de CORS e deve conceder acesso apenas à URL do app público.

* RN02 - A API deve validar os dados recebidos pelo cliente antes de processá-los.

* RN03 - A API deve limitar o máximo de 50 requisições por minuto para todas as rotas.

* RN04 - O frontend deve mostrar fallback e instruções do que fazer sobre um erro quando a API comunicar "Too Many Requests", "Not Found" ou "Internal Server Error".

* RN05 - Cada conta de usuário deve possuir um e-mail único.

* RN06 - O e-mail informado deve possuir formato válido.

* RN07 - Senhas de usuários devem ter pelo menos 8 caracteres, uma letra maiúscula, uma letra minúscula, um número, um caractere especial e tamanho máximo de 100 caracteres.

* RN08 - Ao criar uma conta, o usuário deve receber um código único que deverá armazenar em um lugar seguro, pois esse código será o único meio de recuperar a conta caso esqueça a senha ou queira trocar o endereço de e-mail da conta.

* RN09 - Com seu código único de recuperação, o usuário deve poder trocar o endereço de e-mail da conta, trocar sua senha ou recuperar sua conta em caso de esquecimento da senha.

* RN10 - Contas de usuários que não fizerem login há mais de 12 meses devem ser excluídas permanentemente.

* RN11 - Cada candidatura deve pertencer a apenas um usuário.

* RN12 - Um usuário só pode visualizar, editar ou excluir suas próprias candidaturas.

* RN13 - O título da vaga deve possuir entre 1 e 150 caracteres.

* RN14 - O nome da empresa deve possuir entre 1 e 150 caracteres.

* RN15 - A descrição da vaga deve possuir no máximo 5000 caracteres.

* RN16 - A cultura, os valores ou a filosofia da empresa devem possuir no máximo 5000 caracteres.

* RN17 - O link da vaga deve possuir uma URL válida.

* RN18 - O método de candidatura deve ser selecionado a partir das opções disponíveis no sistema.

* RN19 - As etapas de uma candidatura devem ser selecionadas a partir das etapas predefinidas disponíveis no sistema.

* RN20 - O usuário pode selecionar apenas as etapas que fazem parte do processo seletivo da vaga.

* RN21 - A ordem das etapas selecionadas deve representar a ordem em que o processo seletivo ocorre.

* RN22 - Uma candidatura deve possuir pelo menos uma etapa.

* RN23 - Uma etapa de candidatura deve possuir um dos seguintes estados: pendente, aprovado ou reprovado.

* RN24 - Uma etapa só pode ser marcada como aprovada ou reprovada quando estiver pendente.

* RN25 - Uma etapa reprovada deve possuir um motivo de reprovação quando essa informação for conhecida.

* RN26 - O motivo de reprovação deve ser selecionado a partir das opções disponíveis no sistema ou registrado como outro motivo.

* RN27 - O usuário deve poder registrar o motivo de uma aprovação ou reprovação quando possuir essa informação.

* RN28 - O usuário deve poder registrar se recebeu uma indicação para determinada candidatura.

* RN29 - O usuário deve poder informar qual currículo foi utilizado em cada candidatura.

* RN30 - Uma candidatura pode possuir uma ou mais habilidades exigidas pela vaga.

* RN31 - Uma candidatura excluída deve permanecer na lixeira durante 15 dias antes da exclusão permanente.

* RN32 - Uma candidatura presente na lixeira pode ser restaurada durante o período de 15 dias.

* RN33 - O usuário pode excluir permanentemente uma candidatura presente na lixeira.

* RN34 - Após 15 dias na lixeira, a candidatura deve ser excluída permanentemente.

* RN35 - Uma candidatura excluída não deve aparecer nas listagens normais do sistema.

* RN36 - Uma candidatura restaurada deve voltar a aparecer nas listagens normais do sistema.

* RN37 - O sistema deve disponibilizar etapas predefinidas para os processos seletivos, podendo incluir:

  * Triagem
  * Entrevista com RH
  * Entrevista técnica
  * Teste técnico
  * Entrevista com gestor
  * Entrevista final
  * Proposta

* RN38 - O sistema deve preservar o histórico das etapas das candidaturas.

* RN39 - O sistema deve registrar a data em que uma etapa foi aprovada ou reprovada.

* RN40 - Os gargalos apresentados pelo dashboard devem ser baseados nos dados registrados pelo usuário.

* RN41 - O sistema não deve afirmar que uma determinada etapa foi responsável por uma reprovação quando essa informação não tiver sido registrada ou informada pelo usuário.

* RN42 - Campos obrigatórios não podem ser enviados vazios ou nulos.

* RN43 - O servidor deve rejeitar dados que não estejam de acordo com as regras de validação definidas para cada campo.