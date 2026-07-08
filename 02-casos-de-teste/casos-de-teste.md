# Casos de Teste — Ingressos Dança e Tradição

## 1. Objetivo

Documentar os principais casos de teste funcionais do sistema **Ingressos Dança e Tradição**, validando o fluxo de compra de ingresso, criação de reserva, pagamento manual via Pix/WhatsApp, confirmação administrativa, geração de ticket com QR Code e validação na entrada do evento.

Este documento faz parte do case de QA Manual aplicado a um sistema real.

---

## 2. Ambiente de teste

| Item                  | Informação                 |
| --------------------- | -------------------------- |
| Sistema               | Ingressos Dança e Tradição |
| Ambiente              | Homologação                |
| Navegador             | Microsoft Edge             |
| Sistema operacional   | Windows 10                 |
| Dispositivo adicional | Mobile via DevTools        |
| Responsável           | Yruam Käffer               |
| Data                  | 08/07/2026                 |

---

## 3. Massa de teste padrão

| Campo            | Valor fictício                                            |
| ---------------- | --------------------------------------------------------- |
| Nome             | Mari Teste QA                                            |
| Telefone         | (47) 99999-9999                                           |
| CPF              | CPF fictício válido usado no ambiente de teste            |
| E-mail           | [mari.qa.teste@email.com](mailto:mari.qa.teste@email.com) |
| Tipo de ingresso | Inteira / Meia promocional                                |
| Quantidade       | 1                                                         |
| Pagamento        | Pix manual                                                |

---

## 4. Status possíveis

| Status        | Significado                               |
| ------------- | ----------------------------------------- |
| A executar    | Teste ainda não executado                 |
| Aprovado      | Funcionou conforme esperado               |
| Reprovado     | Não funcionou conforme esperado           |
| Bloqueado     | Não foi possível executar por impedimento |
| Não aplicável | Não se aplica ao ambiente atual           |
|Aprovado ressalva| Funcionalidade principal funcionou, mas foi encontrado problema visual ou melhoria necessária |

---

# 5. Resumo dos casos de teste

| ID     | Funcionalidade | Cenário                                                 | Prioridade | Status     |
| ------ | -------------- | ------------------------------------------------------- | ---------- | ---------- |
| CT-001 | Landing page   | Validar carregamento e informações principais do evento | Alta       | Aprovado   |
| CT-002 | Compra         | Validar seleção de ingresso inteira                     | Alta       | Aprovado   |
| CT-003 | Compra         | Validar seleção de ingresso meia/promocional            | Alta       | Aprovado   |
| CT-004 | Compra         | Validar cálculo do valor total por quantidade           | Alta       | Aprovado   |
| CT-005 | Formulário     | Validar campos obrigatórios vazios                      | Alta       | Aprovado   |
| CT-006 | Formulário     | Validar CPF inválido                                    | Alta       | Aprovado   |
| CT-007 | Reserva        | Criar reserva com dados válidos                         | Alta       | Aprovado   |
| CT-008 | Pagamento      | Validar tela de pagamento Pix/WhatsApp                  | Alta       | Aprovado   |
| CT-009 | Admin          | Localizar reserva no painel administrativo              | Alta       |Aprovado ressalva|
| CT-010 | Admin          | Confirmar pagamento manualmente                         | Alta       | Aprovado   |
| CT-011 | Ticket         | Validar geração de ticket com QR Code                   | Alta       | Reprovado  |
| CT-012 | Validação      | Validar ticket pela primeira vez                        | Alta       | Aprovado   |
| CT-013 | Validação      | Bloquear reutilização de ticket já validado             | Alta       | Aprovado   |
| CT-014 | Mobile         | Validar fluxo principal em tela mobile                  | Média      | Aprovado   |

---

# 6. Casos de teste detalhados

## CT-001 — Validar carregamento e informações principais do evento

**Funcionalidade:** Landing page
**Prioridade:** Alta
**Tipo de teste:** Funcional / Interface

### Pré-condição

O sistema deve estar publicado e acessível pelo navegador.

### Passos

1. Acessar a página inicial do sistema.
2. Aguardar o carregamento completo da página.
3. Verificar se as informações principais do evento são exibidas.
4. Verificar se existe chamada clara para compra de ingressos.
5. Verificar se as informações de local e orientações gerais estão visíveis.

### Resultado esperado

A landing page deve carregar corretamente, sem erro crítico, exibindo as informações principais do evento e direcionando o usuário para o fluxo de compra.

### Status

Aprovado. A landing page é carregada no endereço Vercel de Homologação (https://ingressosdancaetradicao.vercel.app/), as informações referentes ao evento apresentadas estão corretas.

### Evidência

`05-evidencias/casos-de-teste/CT-001.png`

---

## CT-002 — Validar seleção de ingresso inteira

**Funcionalidade:** Compra de ingresso
**Prioridade:** Alta
**Tipo de teste:** Funcional / Regra de negócio

### Pré-condição

A página de compra deve estar acessível.

### Passos

1. Acessar o fluxo de compra.
2. Selecionar o tipo de ingresso "Inteira".
3. Selecionar quantidade igual a 1.
4. Verificar o valor exibido no resumo da compra.

### Resultado esperado

O sistema deve permitir a seleção do ingresso inteira e exibir o valor correspondente corretamente no resumo da compra.

### Status

Aprovado. Ao selecionar o botão comprar ingresso na pagina principal, o usuário é redirecionado a pagina de compra e é possível selecionar o tipo de ingresso e quantidade de ingressos.

### Evidência

`05-evidencias/casos-de-teste/CT-002.png`

---

## CT-003 — Validar seleção de ingresso meia/promocional

**Funcionalidade:** Compra de ingresso
**Prioridade:** Alta
**Tipo de teste:** Funcional / Regra de negócio

### Pré-condição

A página de compra deve estar acessível.

### Passos

1. Acessar o fluxo de compra.
2. Selecionar o tipo de ingresso "Meia" ou "Promocional".
3. Selecionar quantidade igual a 1.
4. Verificar o valor exibido no resumo da compra.

### Resultado esperado

O sistema deve permitir a seleção do ingresso meia/promocional e exibir o valor correspondente corretamente no resumo da compra.

### Status

Aprovado. Ao selecionar o botão comprar ingresso na pagina principal, o usuário é redirecionado a pagina de compra e é possível selecionar o tipo de ingresso e quantidade de ingressos.

### Evidência

`05-evidencias/casos-de-teste/CT-003.png`

---

## CT-004 — Validar cálculo do valor total por quantidade

**Funcionalidade:** Compra de ingresso
**Prioridade:** Alta
**Tipo de teste:** Funcional / Regra de negócio

### Pré-condição

A página de compra deve estar acessível e os tipos de ingresso devem estar disponíveis.

### Passos

1. Acessar o fluxo de compra.
2. Selecionar um tipo de ingresso.
3. Selecionar quantidade maior que 1.
4. Verificar o valor unitário do ingresso.
5. Verificar o valor total exibido.

### Resultado esperado

O sistema deve calcular corretamente o valor total com base no tipo de ingresso selecionado e na quantidade escolhida.

### Status

Aprovado. É possível selecionar o tipo de ingresso e quantidade de ingressos e no resumo da compra é exibido corretamente o valor total do ingressos.

### Evidência

`05-evidencias/casos-de-teste/CT-004.png`

---

## CT-005 — Validar campos obrigatórios vazios

**Funcionalidade:** Formulário do comprador
**Prioridade:** Alta
**Tipo de teste:** Validação de formulário / Teste negativo

### Pré-condição

A página de compra deve estar acessível.

### Passos

1. Acessar o fluxo de compra.
2. Selecionar tipo de ingresso e quantidade.
3. Deixar um ou mais campos obrigatórios vazios.
4. Tentar avançar no fluxo de compra.

### Resultado esperado

O sistema deve impedir o avanço e exibir mensagens de validação para os campos obrigatórios não preenchidos.

### Status

Aprovado. O sistema não permite a compra de ingressos sem todos os dados obrigatórios estarem devidamente preenchidos.

### Evidência

`05-evidencias/casos-de-teste/CT-005.png`

---

## CT-006 — Validar CPF inválido

**Funcionalidade:** Formulário do comprador
**Prioridade:** Alta
**Tipo de teste:** Validação de formulário / Teste negativo

### Pré-condição

A página de compra deve estar acessível.

### Passos

1. Acessar o fluxo de compra.
2. Selecionar tipo de ingresso e quantidade.
3. Preencher nome, telefone e e-mail com dados válidos.
4. Preencher o campo CPF com um valor inválido.
5. Tentar avançar no fluxo de compra.

### Resultado esperado

O sistema deve impedir o avanço e exibir mensagem informando que o CPF é inválido.

### Status

Aprovado. O sistema não avança a compra do ingresso sem o preenchimento correto do CPF.

### Evidência

`05-evidencias/casos-de-teste/CT-006.png`

---

## CT-007 — Criar reserva com dados válidos

**Funcionalidade:** Reserva
**Prioridade:** Alta
**Tipo de teste:** Funcional / Fluxo principal

### Pré-condição

A página de compra deve estar acessível e deve existir capacidade disponível para o evento.

### Passos

1. Acessar o fluxo de compra.
2. Selecionar tipo de ingresso.
3. Selecionar quantidade válida.
4. Preencher nome, telefone, CPF e e-mail com dados fictícios válidos.
5. Confirmar a criação da reserva.

### Resultado esperado

O sistema deve criar a reserva com sucesso e direcionar o usuário para a etapa de pagamento, mantendo o pedido com status pendente de pagamento.

### Status

Aprovado. Preenchendo corretamente os dados o sistema encaminha o usuário a tela de pagamento e cria a reserva no sistema.

### Evidência

`05-evidencias/casos-de-teste/CT-007.png`

---

## CT-008 — Validar tela de pagamento Pix/WhatsApp

**Funcionalidade:** Pagamento
**Prioridade:** Alta
**Tipo de teste:** Funcional / Interface

### Pré-condição

Uma reserva deve ter sido criada com sucesso.

### Passos

1. Criar uma reserva com dados válidos.
2. Acessar a tela de pagamento.
3. Verificar se o QR Code Pix é exibido.
4. Verificar se existem instruções para envio do comprovante via WhatsApp.
5. Verificar se o valor exibido corresponde ao total da compra.

### Resultado esperado

A tela de pagamento deve exibir corretamente o QR Code Pix, o valor da compra e as instruções para envio do comprovante via WhatsApp.

### Status

Aprovado. A página é exibida com informações para pagamento e encaminhamento do comprovante via WhatsApp.

### Evidência

`05-evidencias/casos-de-teste/CT-008.png`

---

## CT-009 — Localizar reserva no painel administrativo

**Funcionalidade:** Área administrativa
**Prioridade:** Alta
**Tipo de teste:** Funcional / Admin

### Pré-condição

Uma reserva deve ter sido criada previamente.

### Passos

1. Acessar a área administrativa.
2. Realizar autenticação, se necessário.
3. Buscar a reserva criada usando nome, código da reserva ou dados do comprador.
4. Verificar se a reserva aparece na listagem administrativa.

### Resultado esperado

O painel administrativo deve permitir localizar a reserva criada, exibindo dados básicos do pedido, status e informações necessárias para conferência.

### Status

Aprovado com ressalva. O painel reservas na seção admin mostra as reservas em aberto que aguardam confirmação e existe busca se necessário, porém existe um bug na barra de busca onde apresenta elementos sobrepostos.

### Evidência

`05-evidencias/casos-de-teste/CT-009.png`
`05-evidencias/bugs/BUG-001.png`

---

## CT-010 — Confirmar pagamento manualmente

**Funcionalidade:** Área administrativa
**Prioridade:** Alta
**Tipo de teste:** Funcional / Admin / Regra de negócio

### Pré-condição

Deve existir uma reserva pendente de pagamento.

### Passos

1. Acessar a área administrativa.
2. Localizar uma reserva pendente.
3. Acionar a confirmação de pagamento.
4. Confirmar a ação.
5. Verificar o novo status do pedido.

### Resultado esperado

O sistema deve alterar o pedido para pago e gerar o ticket correspondente para o comprador.

### Status

Aprovado. Após confirmação manual da compra do ingresso o sistema altera seu status e gera ticket a ser enviado ao comprador.

### Evidência

`05-evidencias/casos-de-teste/CT-010.png`

---

## CT-011 — Validar geração de ticket com QR Code

**Funcionalidade:** Ticket
**Prioridade:** Alta
**Tipo de teste:** Funcional / QR Code

### Pré-condição

O pagamento da reserva deve ter sido confirmado pelo administrador.

### Passos

1. Acessar o link ou página do ticket confirmado.
2. Verificar as informações básicas do ticket.
3. Verificar se o QR Code do ticket é exibido.
4. Conferir se o ticket está associado ao pedido confirmado.

### Resultado esperado

O ticket deve ser exibido corretamente, contendo informações básicas do comprador/ingresso e QR Code para validação na entrada do evento.

### Status

Reprovado. O ticket é gerado em forma de PDF que o usuário receberá. Nele constam todas as informações do evento incluindo o QR Code para liberação. Porém existe um bug visual de linhas de textos sobrepondo com elementos visuais do ticket podendo interferir na experiência do usuário

### Evidência

`05-evidencias/casos-de-teste/CT-011.png`
`05-evidencias/bugs/BUG-002.png`

---

## CT-012 — Validar ticket pela primeira vez

**Funcionalidade:** Validação de ticket
**Prioridade:** Alta
**Tipo de teste:** Funcional / Admin / Regra de negócio

### Pré-condição

Deve existir um ticket confirmado e ainda não utilizado.

### Passos

1. Acessar a área de validação de tickets.
2. Informar ou escanear o código do ticket.
3. Confirmar a validação.
4. Verificar a mensagem exibida pelo sistema.

### Resultado esperado

O sistema deve validar o ticket com sucesso e marcar o ingresso como utilizado.

### Status

Aprovado. É possível validar o ticket através de seu código gerado um resultado de ingresso validado dentro do sistema.

### Evidência

`05-evidencias/casos-de-teste/CT-012.png`

---

## CT-013 — Bloquear reutilização de ticket já validado

**Funcionalidade:** Validação de ticket
**Prioridade:** Alta
**Tipo de teste:** Teste negativo / Regra de negócio

### Pré-condição

Deve existir um ticket já validado anteriormente.

### Passos

1. Acessar a área de validação de tickets.
2. Informar novamente o mesmo código de ticket já utilizado.
3. Tentar validar o ingresso pela segunda vez.

### Resultado esperado

O sistema deve bloquear a segunda validação e informar que o ticket já foi utilizado.

### Status

Aprovado. Quando é tentado validar novamente um ticket já validado é informado pelo sistema que o mesmo ja foi utilizado.

### Evidência

`05-evidencias/casos-de-teste/CT-013.png`

---

## CT-014 — Validar fluxo principal em tela mobile

**Funcionalidade:** Responsividade
**Prioridade:** Média
**Tipo de teste:** Responsivo / Interface

### Pré-condição

O sistema deve estar acessível pelo navegador.

### Passos

1. Abrir o sistema em modo mobile pelo DevTools ou em um smartphone.
2. Acessar a landing page.
3. Acessar o fluxo de compra.
4. Selecionar tipo de ingresso e quantidade.
5. Preencher os dados do comprador.
6. Verificar se os elementos permanecem legíveis e utilizáveis.

### Resultado esperado

O fluxo principal deve permanecer legível, organizado e utilizável em tela mobile, sem quebras visuais que impeçam a compra.

### Status

Aprovado. O fluxo segue corretamente através das telas conforme versão desktop, com todas as informações legíveis.

### Evidência

`05-evidencias/casos-de-teste/CT-014.png`

---

## 7. Resultado da execução

**Total de casos planejados:** 14  
**Aprovados:** 12  
**Aprovados com ressalvas:** 1  
**Reprovados:** 1  
**Bloqueados:** 0  
**Não aplicáveis:** 0  

---

## 8. Observações gerais

Aprovado com ressalvas. O fluxo principal foi validado com sucesso, porém foram encontrados dois bugs visuais documentados: um no campo de busca do painel administrativo e outro no layout do ticket/PDF gerado.

