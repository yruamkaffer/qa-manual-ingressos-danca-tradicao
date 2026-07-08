# Plano de Teste — Ingressos Dança e Tradição

## 1. Objetivo

Validar manualmente as principais funcionalidades do sistema **Ingressos Dança e Tradição**, um MVP web para venda e reserva de ingressos de espetáculo de dança com seleção de tipo de ingresso, quantidade, pagamento manual via Pix/WhatsApp, confirmação administrativa e geração de tickets com QR Code para validação na entrada do evento.

O objetivo deste case é demonstrar a aplicação prática de QA Manual em um sistema real, documentando planejamento, cenários de teste, casos de teste, bug reports, checklists, evidências e relatório final.

---

## 2. Sistema testado

**Nome do sistema:** Ingressos Dança e Tradição
**Tipo de sistema:** Aplicação web para venda e reserva de ingressos
**Tecnologias do projeto:** Next.js, TypeScript, Supabase, PostgreSQL, Tailwind CSS e Vercel
**Fluxo principal:** Escolha do tipo de ingresso → seleção da quantidade → preenchimento dos dados do comprador → criação de reserva → pagamento manual via Pix → envio do comprovante via WhatsApp → confirmação administrativa → geração de ticket com QR Code → validação na entrada do evento

---

## 3. Contexto atual do sistema

O sistema não utiliza mais escolha pública de assentos numerados. Atualmente, o comprador escolhe o **tipo de ingresso** e a **quantidade desejada**.

Os lugares do evento são controlados internamente como capacidade total disponível, com limite de **640 lugares**. Essa capacidade é gerenciada pelo sistema para evitar venda acima do limite disponível, mas o público não escolhe assento específico.

Os assentos/lugares são distribuídos por ordem de chegada no evento.

---

## 4. Escopo dos testes

Serão contemplados neste ciclo de testes manuais os seguintes módulos:

### Área pública

* Landing page do evento
* Informações do espetáculo
* Informações de local e mapa
* Fluxo de compra de ingresso
* Seleção do tipo de ingresso
* Seleção de quantidade
* Validação de limite de quantidade
* Formulário do comprador
* Validação de campos obrigatórios
* Validação de CPF
* Cálculo automático do valor total
* Criação de reserva
* Tela de pagamento com QR Code Pix
* Instruções de envio do comprovante via WhatsApp
* Página de ticket após confirmação administrativa
* Exibição do QR Code do ticket
* Aviso de que os lugares são distribuídos por ordem de chegada

### Área administrativa

* Acesso administrativo protegido por senha/sessão
* Dashboard administrativo
* Busca de reservas por dados do comprador
* Busca por código de reserva
* Busca por código de ticket
* Confirmação manual de pagamento
* Cancelamento de reserva
* Geração de ingresso cortesia
* Controle interno de capacidade
* Exportação CSV de pedidos pagos
* Validação de ticket na entrada
* Controle de ticket já utilizado

### Dados e regras de negócio

* Tipo de ingresso: inteira, meia/promocional e cortesia
* Valor correto por tipo de ingresso
* Quantidade de ingressos selecionada
* Limite máximo de ingressos por compra
* Capacidade interna total do evento
* Prevenção de venda acima da capacidade disponível
* Reserva com status `pending_payment`
* Pedido com status `paid` após confirmação administrativa
* Ticket gerado somente após confirmação do pagamento
* Ticket cortesia gerado somente pela área administrativa
* Ticket cortesia com valor `0`
* QR Code de ticket com dados corretos
* Ticket validado apenas uma vez
* Proteção de dados sensíveis do comprador

### Interface e experiência

* Responsividade em desktop e mobile
* Clareza das mensagens de erro
* Clareza na escolha do tipo de ingresso
* Clareza no cálculo do valor total
* Clareza nas instruções de pagamento
* Clareza na informação sobre lugares por ordem de chegada
* Legibilidade do ticket e do QR Code
* Facilidade de uso no fluxo público e administrativo

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

## 6. Tipos de teste aplicados

| Tipo de teste                    | Objetivo                                                                             |
| -------------------------------- | ------------------------------------------------------------------------------------ |
| Smoke test                       | Verificar se as funcionalidades principais carregam e estão disponíveis              |
| Teste funcional                  | Validar se cada funcionalidade atende ao comportamento esperado                      |
| Teste exploratório               | Navegar livremente pelo sistema buscando falhas e inconsistências                    |
| Teste de regressão               | Verificar se funcionalidades antigas continuam funcionando após alterações           |
| Teste responsivo                 | Validar comportamento em telas menores e dispositivos móveis                         |
| Teste de interface               | Avaliar legibilidade, organização visual e mensagens para o usuário                  |
| Teste de validação de formulário | Verificar campos obrigatórios, formatos inválidos e mensagens de erro                |
| Teste de regra de negócio        | Validar tipo de ingresso, quantidade, valor, reserva, pagamento, ticket e capacidade |
| Teste de QR Code                 | Validar geração, exibição e uso do QR Code do ticket                                 |
| Teste administrativo             | Validar confirmação, cancelamento, cortesia, exportação e validação de tickets       |

---

## 7. Ambiente de teste

| Item                | Informação                                 |
| ------------------- | ------------------------------------------ |
| Sistema             | Ingressos Dança e Tradição                 |
| Ambiente            | Produção / Homologação / Local             |
| Navegador principal | Microsoft Edge                             |
| Navegador adicional | Google Chrome                              |
| Sistema operacional | Windows 10                                 |
| Dispositivo desktop | Notebook/PC                                |
| Dispositivo mobile  | Smartphone ou modo responsivo do DevTools  |
| Banco de dados      | Supabase/PostgreSQL                        |
| Observação          | Utilizar apenas dados fictícios nos testes |

---

## 8. Massa de teste

Os testes devem utilizar compradores fictícios, sem dados pessoais reais.

### Comprador fictício

| Campo    | Valor fictício                                            |
| -------- | --------------------------------------------------------- |
| Nome     | João Teste QA                                             |
| Telefone | (47) 99999-9999                                           |
| CPF      | 000.000.000-00                                            |
| E-mail   | [joao.qa.teste@email.com](mailto:joao.qa.teste@email.com) |

### Compra inteira

| Campo                   | Valor                         |
| ----------------------- | ----------------------------- |
| Tipo de ingresso        | Inteira                       |
| Quantidade              | 1                             |
| Forma de pagamento      | Pix manual                    |
| Status inicial esperado | Reserva pendente de pagamento |
| Status após confirmação | Pago                          |
| Ticket esperado         | Gerado com QR Code            |

### Compra meia/promocional

| Campo                   | Valor                         |
| ----------------------- | ----------------------------- |
| Tipo de ingresso        | Meia/promocional              |
| Quantidade              | 1                             |
| Forma de pagamento      | Pix manual                    |
| Status inicial esperado | Reserva pendente de pagamento |
| Status após confirmação | Pago                          |
| Ticket esperado         | Gerado com QR Code            |

### Compra com múltiplos ingressos

| Campo              | Valor                                                                 |
| ------------------ | --------------------------------------------------------------------- |
| Tipo de ingresso   | Inteira ou meia/promocional                                           |
| Quantidade         | 2 a 10                                                                |
| Resultado esperado | Valor total calculado corretamente e tickets gerados após confirmação |

### Cortesia administrativa

| Campo            | Valor                      |
| ---------------- | -------------------------- |
| Tipo de ingresso | Cortesia                   |
| Origem           | Painel administrativo      |
| Valor            | 0                          |
| Status esperado  | Confirmado automaticamente |
| Ticket esperado  | Gerado com QR Code         |

---

## 9. Critérios de entrada

Os testes podem iniciar quando:

* O sistema estiver acessível pelo navegador.
* A página inicial estiver publicada.
* O fluxo de compra estiver funcional.
* Os tipos de ingresso estiverem cadastrados/configurados.
* A capacidade interna do evento estiver disponível.
* O formulário de compra estiver funcional.
* A tela de pagamento estiver acessível após criação da reserva.
* A área administrativa estiver acessível para teste.
* O fluxo de confirmação manual estiver disponível.
* O fluxo de geração de ticket com QR Code estiver disponível.
* O QA tiver definido a massa de teste.
* O ambiente de teste estiver identificado.

---

## 10. Critérios de saída

O ciclo de testes será considerado finalizado quando:

* Os casos de teste planejados forem executados.
* Os bugs encontrados forem documentados.
* As evidências forem registradas.
* Os fluxos críticos forem validados.
* O relatório final for preenchido.
* Os riscos e limitações forem documentados.
* O status geral do sistema for definido como aprovado, aprovado com ressalvas ou reprovado.

---

## 11. Funcionalidades críticas

As funcionalidades abaixo possuem maior prioridade de validação:

1. Seleção do tipo de ingresso
2. Seleção da quantidade de ingressos
3. Bloqueio de quantidade acima do limite permitido
4. Cálculo correto do valor total
5. Validação dos dados obrigatórios do comprador
6. Validação de CPF inválido
7. Criação de reserva com status pendente de pagamento
8. Exibição correta do QR Code Pix conforme tipo/valor do ingresso
9. Instruções claras para envio do comprovante via WhatsApp
10. Confirmação manual de pagamento pelo administrador
11. Geração de ticket com QR Code após confirmação
12. Controle interno da capacidade total do evento
13. Prevenção de venda acima da capacidade disponível
14. Geração de cortesia pela área administrativa
15. Cortesia com valor `0`
16. Validação de ticket na entrada
17. Bloqueio de segunda validação do mesmo ticket
18. Exportação CSV de pedidos pagos
19. Proteção de dados sensíveis
20. Responsividade do fluxo de compra no mobile

---

## 12. Riscos identificados

| Risco                                           | Impacto                                            |
| ----------------------------------------------- | -------------------------------------------------- |
| Cálculo incorreto do valor total                | Comprador pode pagar valor errado                  |
| QR Code Pix incorreto para o tipo de ingresso   | Pagamento pode ser realizado com valor errado      |
| Comprador selecionar quantidade acima do limite | Pode gerar reserva indevida                        |
| Sistema vender acima da capacidade total        | Superlotação ou controle incorreto do evento       |
| Reserva pendente não expirar automaticamente    | Capacidade pode ficar presa indevidamente          |
| Admin confirmar pagamento errado                | Ticket pode ser gerado indevidamente               |
| Ticket QR Code conter dados sensíveis demais    | Risco de privacidade                               |
| Ticket ser validado mais de uma vez             | Possível entrada duplicada no evento               |
| Cortesia ser gerada sem controle adequado       | Perda de controle operacional                      |
| CSV exportado com dados incorretos              | Organização pode perder controle dos participantes |
| Falha no mobile                                 | Comprador pode não conseguir finalizar a reserva   |
| Dados de CPF expostos desnecessariamente        | Risco de privacidade                               |
| Service role key exposta no frontend            | Risco crítico de segurança                         |
| Pix placeholder em produção                     | Usuário pode tentar pagar usando QR Code inválido  |

---

## 13. Estratégia de execução

A execução dos testes será feita na seguinte ordem:

1. Smoke test geral do sistema
2. Testes da área pública
3. Testes do fluxo de compra
4. Testes de seleção de tipo de ingresso
5. Testes de quantidade
6. Testes de validação de formulário
7. Testes de cálculo de valor total
8. Testes de criação de reserva
9. Testes da tela de pagamento Pix/WhatsApp
10. Testes da área administrativa
11. Testes de confirmação manual de pagamento
12. Testes de geração de ticket com QR Code
13. Testes de validação de ticket
14. Testes de revalidação de ticket já usado
15. Testes de cortesia administrativa
16. Testes de exportação CSV
17. Testes de capacidade interna
18. Testes mobile
19. Testes exploratórios
20. Testes de regressão
21. Registro de bugs
22. Relatório final

---

## 14. Principais cenários de teste planejados

| ID     | Cenário                                        | Resultado esperado                                  |
| ------ | ---------------------------------------------- | --------------------------------------------------- |
| CT-001 | Acessar a landing page                         | Página deve carregar com informações do evento      |
| CT-002 | Selecionar ingresso inteira                    | Sistema deve aplicar o valor da inteira             |
| CT-003 | Selecionar ingresso meia/promocional           | Sistema deve aplicar o valor da meia/promocional    |
| CT-004 | Selecionar quantidade válida                   | Sistema deve atualizar o valor total corretamente   |
| CT-005 | Selecionar quantidade acima do limite          | Sistema deve bloquear ou exibir mensagem de erro    |
| CT-006 | Enviar formulário com dados válidos            | Sistema deve criar reserva pendente                 |
| CT-007 | Enviar formulário com CPF inválido             | Sistema deve exibir erro de validação               |
| CT-008 | Enviar formulário com campo obrigatório vazio  | Sistema deve impedir o envio                        |
| CT-009 | Acessar página de pagamento após reserva       | Sistema deve exibir QR Code Pix e instruções        |
| CT-010 | Confirmar pagamento no admin                   | Pedido deve virar pago e gerar ticket               |
| CT-011 | Acessar ticket confirmado                      | Ticket deve exibir QR Code                          |
| CT-012 | Validar ticket pela primeira vez               | Sistema deve marcar ticket como utilizado           |
| CT-013 | Validar o mesmo ticket novamente               | Sistema deve informar que o ticket já foi utilizado |
| CT-014 | Criar cortesia no admin                        | Sistema deve gerar ticket cortesia com valor 0      |
| CT-015 | Exportar CSV de pedidos pagos                  | CSV deve conter os pedidos confirmados              |
| CT-016 | Tentar reservar acima da capacidade disponível | Sistema deve impedir venda acima da capacidade      |
| CT-017 | Acessar fluxo de compra no mobile              | Fluxo deve estar legível e utilizável               |
| CT-018 | Validar aviso de lugares por ordem de chegada  | Informação deve estar clara para o comprador        |

---

## 15. Resultado esperado do ciclo

Ao final do ciclo, espera-se ter uma visão clara sobre a qualidade do sistema, incluindo:

* Funcionalidades aprovadas
* Funcionalidades com falhas
* Bugs encontrados
* Riscos do MVP
* Melhorias recomendadas
* Evidências dos testes
* Conclusão sobre a estabilidade do fluxo principal de compra, confirmação, geração e validação de ingressos
