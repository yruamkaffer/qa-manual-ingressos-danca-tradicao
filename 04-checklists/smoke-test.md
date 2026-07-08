# Smoke Test — Ingressos Dança e Tradição

## 1. Objetivo

Validar rapidamente se o sistema **Ingressos Dança e Tradição** está minimamente funcional para seguir com os testes manuais detalhados.

O smoke test tem foco no fluxo principal do sistema: acesso ao site, compra de ingresso, criação de reserva, pagamento manual, confirmação administrativa e geração de ticket.

---

## 2. Ambiente de teste

| Item                  | Informação                     |
| --------------------- | ------------------------------ |
| Sistema               | Ingressos Dança e Tradição     |
| Ambiente              | Homologação                    |
| Navegador             | Microsoft Edge                 |
| Sistema operacional   | Windows 10                     |
| Dispositivo adicional | Mobile via DevTools            |
| Responsável           | Yruam Käffer                   |
| Data                  | 08/07/2026                     |

---

## 3. Massa de teste

| Campo            | Valor fictício                                            |
| ---------------- | --------------------------------------------------------- |
| Nome             | João Teste QA                                             |
| Telefone         | (47) 99999-9999                                           |
| CPF              | CPF fictício válido usado no ambiente de teste            |
| E-mail           | [joao.qa.teste@email.com](mailto:joao.qa.teste@email.com) |
| Tipo de ingresso | Inteira                                                   |
| Quantidade       | 1                                                         |
| Pagamento        | Pix manual                                                |

---

## 4. Checklist de Smoke Test

| ID      | Área         | Teste                                     | Resultado esperado                                                | Status     | Evidência |
| ------- | ------------ | ----------------------------------------- | ----------------------------------------------------------------- | ---------- | --------- |
| SMK-001 | Landing page | Acessar a página inicial do evento        | A página deve carregar sem erro crítico                           | Aprovado   |05-evidencias/smoke-test/SMK-001.png|
| SMK-002 | Compra       | Acessar o fluxo de compra                 | A página de compra deve carregar corretamente                     | Aprovado   |05-evidencias/smoke-test/SMK-002.png|
| SMK-003 | Compra       | Selecionar tipo de ingresso e quantidade  | O sistema deve permitir seleção e atualizar o valor total         | Aprovado   |05-evidencias/smoke-test/SMK-003.png|
| SMK-004 | Formulário   | Preencher dados fictícios válidos         | O sistema deve permitir avançar no fluxo                          | Aprovado   |05-evidencias/smoke-test/SMK-004.png|
| SMK-005 | Reserva      | Criar uma reserva                         | A reserva deve ser criada com status pendente de pagamento        | Aprovado   |05-evidencias/smoke-test/SMK-005.png|
| SMK-006 | Pagamento    | Visualizar tela de pagamento Pix/WhatsApp | A tela deve exibir instruções de pagamento e envio de comprovante | Aprovado   |05-evidencias/smoke-test/SMK-006.png|
| SMK-007 | Admin        | Acessar área administrativa               | O painel admin deve carregar após autenticação                    | Aprovado   |05-evidencias/smoke-test/SMK-007.png|
| SMK-008 | Admin        | Localizar e confirmar uma reserva         | O sistema deve alterar o pedido para pago e gerar ticket          | Aprovado   |05-evidencias/smoke-test/SMK-008.png|
| SMK-009 | Ticket       | Acessar o ticket confirmado               | O ticket deve exibir informações básicas e QR Code                | Aprovado   |05-evidencias/smoke-test/SMK-009.png|
| SMK-010 | Mobile       | Validar fluxo principal em tela mobile    | O fluxo deve permanecer legível e utilizável                      | Aprovado   |05-evidencias/smoke-test/SMK-010.png|

---

## 5. Status possíveis

| Status        | Significado                     |
| ------------- | ------------------------------- |
| A executar    | Teste ainda não executado       |
| Aprovado      | Funcionou conforme esperado     |
| Reprovado     | Não funcionou conforme esperado |
| Bloqueado     | Não foi possível executar       |
| Não aplicável | Não se aplica ao ambiente atual |

---

## 6. Resultado da execução

**Total de testes planejados:** 10
**Aprovados:** 10
**Reprovados:** 0
**Bloqueados:** 0
**Não aplicáveis:** 0

---

## 7. Bugs encontrados durante o smoke test

| ID do bug     | Resumo                                             | Severidade    | Prioridade    | Status        |
| ------------- | -------------------------------------------------- | ------------- | ------------- | ------------- |
| Não aplicável | Nenhum bug crítico encontrado durante o smoke test | Não aplicável | Não aplicável | Não aplicável |

---

## 8. Conclusão

**Resultado geral:** Aprovado

**Observações:**

O sistema está apto para seguir para os testes funcionais detalhados.

Durante o smoke test, o fluxo principal foi validado com sucesso: acesso ao sistema, fluxo de compra, criação de reserva, visualização do pagamento, confirmação administrativa, geração de ticket e validação básica em ambiente mobile via DevTools.
