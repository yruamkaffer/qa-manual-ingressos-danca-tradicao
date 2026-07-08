# Plano de Teste — Ingressos Dança e Tradição

## 1. Objetivo

Validar manualmente as principais funcionalidades do sistema **Ingressos Dança e Tradição**, um MVP web para venda e reserva de ingressos de espetáculo de dança com seleção de tipo de ingresso, quantidade, pagamento manual via Pix/WhatsApp, confirmação administrativa e geração de tickets com QR Code para validação na entrada do evento.

O objetivo deste case é demonstrar a aplicação prática de QA Manual em um sistema real, documentando planejamento, escopo, riscos, estratégia de execução, casos de teste, bug reports, evidências e relatório final.

---

## 2. Sistema testado

| Item                   | Informação                                                                                                                                                                                                                                                                   |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nome do sistema        | Ingressos Dança e Tradição                                                                                                                                                                                                                                                   |
| Tipo de sistema        | Aplicação web para venda e reserva de ingressos                                                                                                                                                                                                                              |
| Tecnologias do projeto | Next.js, TypeScript, Supabase, PostgreSQL, Tailwind CSS e Vercel                                                                                                                                                                                                             |
| Fluxo principal        | Escolha do tipo de ingresso → seleção da quantidade → preenchimento dos dados do comprador → criação de reserva → pagamento manual via Pix → envio do comprovante via WhatsApp → confirmação administrativa → geração de ticket com QR Code → validação na entrada do evento |

---

## 3. Contexto atual do sistema

O sistema não utiliza escolha pública de assentos numerados. Atualmente, o comprador escolhe o **tipo de ingresso** e a **quantidade desejada**.

Os lugares do evento são controlados internamente como capacidade total disponível, com limite de **640 lugares**. Essa capacidade é gerenciada pelo sistema para evitar venda acima do limite disponível, mas o público não escolhe assento específico.

Os lugares são distribuídos por ordem de chegada no evento.

---

## 4. Escopo dos testes

Este primeiro ciclo de testes manuais contempla os fluxos principais da área pública e da área administrativa, com foco em validar se o sistema está apto para uso básico no processo de compra, confirmação e validação de ingressos.

### Área pública

* Landing page do evento
* Informações principais do espetáculo
* Fluxo de compra de ingresso
* Seleção do tipo de ingresso
* Seleção de quantidade
* Formulário do comprador
* Validação de campos obrigatórios
* Validação de CPF inválido
* Cálculo automático do valor total
* Criação de reserva
* Tela de pagamento Pix/WhatsApp
* Página de ticket após confirmação administrativa
* Exibição do QR Code do ticket
* Responsividade do fluxo principal em tela mobile

### Área administrativa

* Acesso ao painel administrativo
* Busca/localização de reservas
* Confirmação manual de pagamento
* Geração de ticket após confirmação
* Validação de ticket
* Bloqueio de reutilização de ticket já validado

### Dados e regras de negócio

* Tipo de ingresso: inteira e meia/promocional
* Quantidade de ingressos selecionada
* Cálculo do valor total
* Reserva com status pendente de pagamento
* Pedido com status pago após confirmação administrativa
* Ticket gerado somente após confirmação do pagamento
* QR Code de ticket exibido corretamente
* Ticket validado apenas uma vez

### Interface e experiência

* Clareza na escolha do tipo de ingresso
* Clareza no cálculo do valor total
* Clareza nas instruções de pagamento
* Legibilidade do ticket e do QR Code
* Facilidade de uso no fluxo público e administrativo
* Responsividade em desktop e mobile

---

## 5. Fora do escopo

Não serão contemplados neste primeiro ciclo:

* Testes automatizados
* Testes de carga/performance avançada
* Testes de segurança profunda
* Testes com pagamento Pix real
* Testes de integração com gateway de pagamento
* Testes em todos os navegadores existentes
* Testes de acessibilidade avançada
* Auditoria completa de banco de dados
* Validação com dados pessoais reais
* Validação de leitura real do QR Code em catraca física
* Validação de envio automático de e-mail
* Escolha pública de assento numerado
* Mapa público de assentos

---

## 6. Pontos mapeados para ciclos futuros

Algumas funcionalidades e riscos foram identificados como importantes para o produto, mas não foram priorizados neste primeiro ciclo funcional enxuto.

Esses pontos podem ser explorados em ciclos futuros de QA:

* Geração de cortesia administrativa
* Exportação CSV de pedidos pagos
* Validação completa de capacidade máxima do evento
* Cancelamento de reserva
* Testes de diferentes combinações de quantidade
* Testes mais detalhados de segurança
* Testes de acessibilidade
* Testes em outros navegadores
* Testes automatizados
* Testes de regressão após correção dos bugs encontrados

---

## 7. Tipos de teste aplicados

| Tipo de teste                    | Objetivo                                                                 |
| -------------------------------- | ------------------------------------------------------------------------ |
| Smoke test                       | Verificar se as funcionalidades principais carregam e estão disponíveis  |
| Teste funcional                  | Validar se cada funcionalidade atende ao comportamento esperado          |
| Teste exploratório               | Navegar livremente pelo sistema buscando falhas e inconsistências        |
| Teste responsivo                 | Validar comportamento em tela mobile                                     |
| Teste de interface               | Avaliar legibilidade, organização visual e mensagens para o usuário      |
| Teste de validação de formulário | Verificar campos obrigatórios e formatos inválidos                       |
| Teste de regra de negócio        | Validar tipo de ingresso, quantidade, valor, reserva, pagamento e ticket |
| Teste de QR Code                 | Validar geração, exibição e uso do QR Code do ticket                     |
| Teste administrativo             | Validar busca de reserva, confirmação de pagamento e validação de ticket |

---

## 8. Ambiente de teste

| Item                | Informação                                 |
| ------------------- | ------------------------------------------ |
| Sistema             | Ingressos Dança e Tradição                 |
| Ambiente            | Homologação                                |
| Navegador principal | Microsoft Edge                             |
| Sistema operacional | Windows 10                                 |
| Dispositivo desktop | Notebook/PC                                |
| Dispositivo mobile  | Mobile via DevTools                        |
| Banco de dados      | Supabase/PostgreSQL                        |
| Responsável         | Yruam Käffer                               |
| Data da execução    | 08/07/2026                                 |
| Observação          | Utilizar apenas dados fictícios nos testes |

---

## 9. Massa de teste

Os testes devem utilizar compradores fictícios, sem dados pessoais reais.

| Campo                   | Valor fictício                                            |
| ----------------------- | --------------------------------------------------------- |
| Nome                    | Mari Teste QA                                             |
| Telefone                | (47) 99999-9999                                           |
| CPF                     | CPF fictício válido usado no ambiente de teste            |
| E-mail                  | [mari.qa.teste@email.com](mailto:mari.qa.teste@email.com) |
| Tipo de ingresso        | Inteira / Meia promocional                                |
| Quantidade              | 1                                                         |
| Forma de pagamento      | Pix manual                                                |
| Status inicial esperado | Reserva pendente de pagamento                             |
| Status após confirmação | Pago                                                      |
| Ticket esperado         | Gerado com QR Code                                        |

---

## 10. Critérios de entrada

Os testes podem iniciar quando:

* O sistema estiver acessível pelo navegador.
* A página inicial estiver publicada.
* O fluxo de compra estiver funcional.
* Os tipos de ingresso estiverem disponíveis.
* O formulário de compra estiver funcional.
* A tela de pagamento estiver acessível após criação da reserva.
* A área administrativa estiver acessível para teste.
* O fluxo de confirmação manual estiver disponível.
* O fluxo de geração de ticket com QR Code estiver disponível.
* O QA tiver definido a massa de teste.
* O ambiente de teste estiver identificado.

---

## 11. Critérios de saída

O ciclo de testes será considerado finalizado quando:

* O smoke test for executado.
* Os casos de teste planejados forem executados.
* Os bugs encontrados forem documentados.
* As evidências forem registradas.
* Os fluxos críticos forem validados.
* O relatório final for preenchido.
* Os riscos e limitações forem documentados.
* O status geral do sistema for definido como aprovado, aprovado com ressalvas ou reprovado.

---

## 12. Funcionalidades críticas

As funcionalidades abaixo possuem maior prioridade de validação neste ciclo:

1. Carregamento da landing page
2. Acesso ao fluxo de compra
3. Seleção do tipo de ingresso
4. Seleção da quantidade
5. Cálculo correto do valor total
6. Validação dos dados obrigatórios do comprador
7. Validação de CPF inválido
8. Criação de reserva com status pendente de pagamento
9. Exibição da tela de pagamento Pix/WhatsApp
10. Confirmação manual de pagamento pelo administrador
11. Geração de ticket com QR Code após confirmação
12. Validação de ticket na entrada
13. Bloqueio de segunda validação do mesmo ticket
14. Responsividade do fluxo principal em tela mobile

---

## 13. Riscos identificados

| Risco                                        | Impacto                                                       |
| -------------------------------------------- | ------------------------------------------------------------- |
| Cálculo incorreto do valor total             | Comprador pode pagar valor errado                             |
| QR Code Pix incorreto ou confuso             | Pagamento pode ser realizado de forma incorreta               |
| Dados inválidos no formulário                | Reserva pode ser criada com informações incorretas            |
| Admin confirmar pagamento errado             | Ticket pode ser gerado indevidamente                          |
| Ticket ser validado mais de uma vez          | Possível entrada duplicada no evento                          |
| Ticket/PDF com problema visual               | Comprador pode ter dificuldade de leitura do ingresso         |
| Campo de busca admin com problema visual     | Administrador pode ter pior experiência no painel             |
| Falha no mobile                              | Comprador pode não conseguir finalizar a reserva pelo celular |
| Reserva pendente não expirar automaticamente | Capacidade pode ficar presa indevidamente                     |
| Sistema vender acima da capacidade total     | Superlotação ou controle incorreto do evento                  |
| Dados de CPF expostos desnecessariamente     | Risco de privacidade                                          |
| Pix placeholder em produção                  | Usuário pode tentar pagar usando QR Code inválido             |

---

## 14. Estratégia de execução

A execução dos testes será feita na seguinte ordem:

1. Smoke test geral do sistema
2. Testes da área pública
3. Testes do fluxo de compra
4. Testes de seleção de tipo de ingresso
5. Testes de quantidade e cálculo do valor total
6. Testes de validação de formulário
7. Testes de criação de reserva
8. Testes da tela de pagamento Pix/WhatsApp
9. Testes da área administrativa
10. Testes de confirmação manual de pagamento
11. Testes de geração de ticket com QR Code
12. Testes de validação de ticket
13. Testes de revalidação de ticket já usado
14. Teste do fluxo principal em tela mobile
15. Registro de bugs encontrados
16. Relatório final

---

## 15. Casos de teste priorizados neste ciclo

Neste primeiro ciclo, foram priorizados 14 casos de teste funcionais, cobrindo o fluxo principal do sistema.

| ID     | Cenário                                                 | Resultado esperado                                                     |
| ------ | ------------------------------------------------------- | ---------------------------------------------------------------------- |
| CT-001 | Validar carregamento e informações principais do evento | Landing page deve carregar corretamente e exibir informações do evento |
| CT-002 | Validar seleção de ingresso inteira                     | Sistema deve permitir seleção e aplicar valor correspondente           |
| CT-003 | Validar seleção de ingresso meia/promocional            | Sistema deve permitir seleção e aplicar valor correspondente           |
| CT-004 | Validar cálculo do valor total por quantidade           | Sistema deve calcular corretamente o valor total                       |
| CT-005 | Validar campos obrigatórios vazios                      | Sistema deve impedir avanço e exibir validação                         |
| CT-006 | Validar CPF inválido                                    | Sistema deve impedir avanço e exibir mensagem de CPF inválido          |
| CT-007 | Criar reserva com dados válidos                         | Sistema deve criar reserva e direcionar para pagamento                 |
| CT-008 | Validar tela de pagamento Pix/WhatsApp                  | Sistema deve exibir QR Code Pix e instruções de envio do comprovante   |
| CT-009 | Localizar reserva no painel administrativo              | Admin deve conseguir localizar a reserva criada                        |
| CT-010 | Confirmar pagamento manualmente                         | Sistema deve alterar pedido para pago e gerar ticket                   |
| CT-011 | Validar geração de ticket com QR Code                   | Ticket deve ser gerado com informações básicas e QR Code               |
| CT-012 | Validar ticket pela primeira vez                        | Sistema deve validar o ticket e marcar como utilizado                  |
| CT-013 | Bloquear reutilização de ticket já validado             | Sistema deve impedir segunda validação do mesmo ticket                 |
| CT-014 | Validar fluxo principal em tela mobile                  | Fluxo deve permanecer legível e utilizável em tela mobile              |

---

## 16. Resultado esperado do ciclo

Ao final do ciclo, espera-se ter uma visão clara sobre a qualidade do sistema, incluindo:

* Funcionalidades aprovadas
* Funcionalidades aprovadas com ressalvas
* Funcionalidades reprovadas
* Bugs encontrados
* Riscos do MVP
* Melhorias recomendadas
* Evidências dos testes
* Conclusão sobre a estabilidade do fluxo principal de compra, confirmação, geração e validação de ingressos

---

## 17. Status final esperado

O status final do ciclo deverá ser definido no relatório final como:

* **Aprovado**, caso os fluxos críticos funcionem sem falhas relevantes;
* **Aprovado com ressalvas**, caso o fluxo principal funcione, mas existam bugs ou melhorias documentadas;
* **Reprovado**, caso alguma funcionalidade crítica esteja bloqueada ou inutilizável.
