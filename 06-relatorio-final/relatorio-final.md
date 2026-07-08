# Relatório Final de Testes — Ingressos Dança e Tradição

## 1. Objetivo

Este relatório apresenta o resultado final da execução dos testes manuais realizados no sistema **Ingressos Dança e Tradição**, um MVP web para reserva e venda de ingressos de espetáculo de dança.

O objetivo dos testes foi validar o fluxo principal do sistema, incluindo acesso ao evento, compra de ingresso, criação de reserva, pagamento manual via Pix/WhatsApp, confirmação administrativa, geração de ticket com QR Code e validação do ingresso.

---

## 2. Sistema testado

| Item                  | Informação                                |
| --------------------- | ----------------------------------------- |
| Sistema               | Ingressos Dança e Tradição                |
| Tipo                  | MVP web para reserva e venda de ingressos |
| Ambiente              | Homologação                               |
| Navegador             | Microsoft Edge                            |
| Sistema operacional   | Windows 10                                |
| Dispositivo adicional | Mobile via DevTools                       |
| Responsável           | Yruam Käffer                              |
| Data da execução      | 08/07/2026                                |

---

## 3. Escopo validado

Durante o ciclo de testes, foram validadas as seguintes áreas do sistema:

* Landing page do evento
* Fluxo de compra de ingresso
* Seleção de tipo de ingresso
* Seleção de quantidade
* Cálculo do valor total
* Formulário do comprador
* Validação de campos obrigatórios
* Validação de CPF inválido
* Criação de reserva
* Tela de pagamento Pix/WhatsApp
* Painel administrativo
* Busca de reservas
* Confirmação manual de pagamento
* Geração de ticket com QR Code
* Validação de ticket
* Bloqueio de reutilização de ticket validado
* Fluxo principal em tela mobile

---

## 4. Fora do escopo

Neste ciclo de testes, não foram contemplados:

* Testes automatizados
* Testes de carga
* Testes de performance avançada
* Testes de segurança profunda
* Testes com Pix real
* Integração com gateway de pagamento
* Auditoria completa no banco de dados
* Testes em múltiplos navegadores
* Testes com dados pessoais reais

---

## 5. Massa de teste utilizada

Os testes foram executados utilizando apenas dados fictícios em ambiente de homologação.

| Campo            | Valor                                                     |
| ---------------- | --------------------------------------------------------- |
| Nome             | Mari Teste QA                                             |
| Telefone         | (47) 99999-9999                                           |
| CPF              | CPF fictício válido usado no ambiente de teste            |
| E-mail           | [mari.qa.teste@email.com](mailto:mari.qa.teste@email.com) |
| Tipo de ingresso | Meia promocional                                          |
| Quantidade       | 1 ou mais ingressos                                       |
| Pagamento        | Pix manual                                                |

| Campo            | Valor                                                     |
| ---------------- | --------------------------------------------------------- |
| Nome             | João Teste QA                                             |
| Telefone         | (47) 99999-9999                                           |
| CPF              | CPF fictício válido usado no ambiente de teste            |
| E-mail           | [joao.qa.teste@email.com](mailto:joao.qa.teste@email.com) |
| Tipo de ingresso | Inteira                                                   |
| Quantidade       | 1 ingresso                                                |
| Pagamento        | Pix manual                                                |

Nenhum dado pessoal real foi utilizado durante a execução dos testes.

---

## 6. Resumo da execução

### Smoke Test

| Resultado                  | Quantidade |
| -------------------------- | ---------: |
| Total de testes planejados |         10 |
| Aprovados                  |         10 |
| Reprovados                 |          0 |
| Bloqueados                 |          0 |
| Não aplicáveis             |          0 |

O smoke test foi aprovado, indicando que o sistema estava minimamente funcional para seguir com os testes manuais detalhados.

---

### Casos de Teste Funcionais

| Resultado                 | Quantidade |
| ------------------------- | ---------: |
| Total de casos planejados |         14 |
| Aprovados                 |         12 |
| Aprovados com ressalva    |          1 |
| Reprovados                |          1 |
| Bloqueados                |          0 |
| Não aplicáveis            |          0 |

---

## 7. Casos com ressalva ou reprovação

| ID     | Funcionalidade      | Resultado             | Observação                                                                             |
| ------ | ------------------- | --------------------- | -------------------------------------------------------------------------------------- |
| CT-009 | Área administrativa | Aprovado com ressalva | A busca de reservas funciona, porém foi identificado bug visual no campo de busca      |
| CT-011 | Ticket              | Reprovado             | O ticket é gerado com QR Code, porém apresenta sobreposição de textos no layout do PDF |

---

## 8. Bugs encontrados

Durante a execução dos testes funcionais, foram identificados dois bugs visuais.

| ID      | Resumo                                                               | Severidade | Prioridade | Status |
| ------- | -------------------------------------------------------------------- | ---------- | ---------- | ------ |
| BUG-001 | Texto da barra de busca sobreposto ao ícone no painel administrativo | Baixa      | Média      | Aberto |
| BUG-002 | Sobreposição de textos no ticket/PDF gerado                          | Média      | Alta       | Aberto |

---

## 9. Detalhamento dos bugs

### BUG-001 — Texto da barra de busca sobreposto ao ícone no painel administrativo

**Funcionalidade:** Área administrativa / Reservas
**Tipo:** Visual / Interface
**Severidade:** Baixa
**Prioridade:** Média
**Status:** Aberto

**Descrição:**
Na tela de reservas do painel administrativo, o texto do campo de busca aparece sobreposto ou muito próximo ao ícone, prejudicando a legibilidade e o acabamento visual do componente.

**Impacto:**
O bug não impede a busca de reservas, mas afeta a experiência visual do administrador e transmite menor percepção de qualidade na interface.

**Evidência:**
`05-evidencias/bugs/BUG-001.png`

---

### BUG-002 — Sobreposição de textos no ticket/PDF gerado

**Funcionalidade:** Ticket / PDF do ingresso
**Tipo:** Visual / Layout
**Severidade:** Média
**Prioridade:** Alta
**Status:** Aberto

**Descrição:**
No ticket/PDF gerado após confirmação administrativa, há sobreposição de textos no cabeçalho, afetando a leitura das informações do evento.

**Impacto:**
O ticket é o documento final enviado ao comprador e utilizado no dia do evento. A sobreposição visual pode gerar confusão na leitura e prejudicar a percepção de qualidade do sistema.

**Evidência:**
`05-evidencias/bugs/BUG-002.png`

---

## 10. Pontos positivos observados

Durante os testes, foram observados os seguintes pontos positivos:

* Landing page carregando corretamente
* Fluxo de compra acessível
* Seleção de tipo de ingresso funcionando
* Cálculo do valor total funcionando
* Validação de campos obrigatórios funcionando
* Validação de CPF inválido funcionando
* Criação de reserva funcionando
* Tela de pagamento Pix/WhatsApp exibida corretamente
* Reserva localizada no painel administrativo
* Confirmação manual de pagamento funcionando
* Ticket gerado após confirmação administrativa
* QR Code exibido no ticket
* Validação de ticket funcionando
* Bloqueio de reutilização de ticket funcionando
* Fluxo principal utilizável em tela mobile

---

## 11. Riscos e pontos de atenção

Mesmo com o fluxo principal funcionando, alguns pontos merecem atenção em ciclos futuros:

| Risco                                                    | Impacto                                              |
| -------------------------------------------------------- | ---------------------------------------------------- |
| Layout do ticket com sobreposição                        | Pode prejudicar a leitura do ingresso pelo comprador |
| Campo de busca admin desalinhado                         | Pode afetar a experiência do administrador           |
| Validação apenas manual de pagamento                     | Exige atenção operacional da equipe                  |
| Fluxo dependente de WhatsApp                             | Pode gerar atrasos na confirmação                    |
| Ticket com QR Code precisa ser validado com cuidado      | Evita reutilização indevida                          |
| Capacidade do evento precisa ser controlada corretamente | Evita venda acima do limite disponível               |

---

## 12. Conclusão

O sistema **Ingressos Dança e Tradição** foi considerado **aprovado com ressalvas** neste ciclo de testes manuais.

O fluxo principal do sistema funcionou corretamente, incluindo compra de ingresso, criação de reserva, pagamento manual, confirmação administrativa, geração de ticket e validação do ingresso.

Apesar disso, foram encontrados dois bugs visuais que devem ser corrigidos para melhorar a qualidade da interface e a experiência final do usuário/admin, principalmente o problema de sobreposição de textos no ticket/PDF gerado, por se tratar do documento final enviado ao comprador.

---

## 13. Recomendação final

Recomenda-se corrigir os bugs encontrados antes de considerar o sistema visualmente finalizado para uso em produção.

Prioridade recomendada:

1. Corrigir a sobreposição de textos no ticket/PDF gerado.
2. Ajustar o campo de busca do painel administrativo.
3. Realizar reteste dos bugs corrigidos.
4. Executar uma regressão rápida no fluxo de compra, admin e ticket.
5. Atualizar este relatório após a correção e reteste.

---

## 14. Status final do ciclo

**Resultado geral:** Aprovado com ressalvas

**Motivo:**
As funcionalidades críticas foram validadas e o fluxo principal está operacional, porém existem bugs visuais documentados que impactam a qualidade percebida do sistema.

---
