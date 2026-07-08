# Plano de Teste — Ingressos Dança e Tradição

## 1. Objetivo

Validar manualmente as principais funcionalidades do sistema **Ingressos Dança e Tradição**, um MVP web para reserva e venda de ingressos de espetáculo de dança com escolha de assentos numerados, pagamento manual via Pix/WhatsApp, confirmação administrativa e geração de tickets.

O objetivo deste case é demonstrar a aplicação prática de QA Manual em um sistema real, documentando planejamento, cenários de teste, casos de teste, bug reports, checklists, evidências e relatório final.

---

## 2. Sistema testado

**Nome do sistema:** Ingressos Dança e Tradição
**Tipo de sistema:** Aplicação web para reserva e venda de ingressos
**Tecnologias do projeto:** Next.js, TypeScript, Supabase, Tailwind CSS e Vercel
**Fluxo principal:** Escolha de assento → preenchimento de dados → reserva → pagamento manual via Pix → envio de comprovante via WhatsApp → confirmação admin → geração de ticket

---

## 3. Escopo dos testes

Serão contemplados neste ciclo de testes manuais os seguintes módulos:

### Área pública

* Landing page do evento
* Informações do espetáculo
* Mapa de assentos
* Seleção de assentos disponíveis
* Formulário do comprador
* Validação de campos obrigatórios
* Cálculo automático do valor total
* Criação de reserva
* Tela de instruções de pagamento Pix/WhatsApp
* Página de ticket após confirmação

### Área administrativa

* Acesso administrativo
* Dashboard admin
* Busca de reservas
* Confirmação manual de pagamento
* Cancelamento de reserva
* Bloqueio de assentos
* Desbloqueio de assentos
* Exportação CSV
* Validação de ticket
* Controle de ticket utilizado

### Dados e regras de negócio

* Status dos assentos: disponível, reservado, vendido e bloqueado
* Prevenção de reserva duplicada para o mesmo assento
* Geração de código de reserva
* Geração de código de ticket após pagamento
* Tratamento de dados sensíveis do comprador

### Interface e experiência

* Responsividade em desktop e mobile
* Clareza das mensagens de erro
* Legibilidade do mapa de assentos
* Fluxo de compra compreensível para o usuário

---

## 4. Fora do escopo

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

---

## 5. Tipos de teste aplicados

| Tipo de teste                    | Objetivo                                                                   |
| -------------------------------- | -------------------------------------------------------------------------- |
| Smoke test                       | Verificar se as funcionalidades principais carregam e estão disponíveis    |
| Teste funcional                  | Validar se cada funcionalidade atende ao comportamento esperado            |
| Teste exploratório               | Navegar livremente pelo sistema buscando falhas e inconsistências          |
| Teste de regressão               | Verificar se funcionalidades antigas continuam funcionando após alterações |
| Teste responsivo                 | Validar comportamento em telas menores e dispositivos móveis               |
| Teste de interface               | Avaliar legibilidade, organização visual e mensagens para o usuário        |
| Teste de validação de formulário | Verificar campos obrigatórios, formatos inválidos e mensagens de erro      |
| Teste de regra de negócio        | Validar status de assentos, reserva, pagamento, ticket e uso do ingresso   |

---

## 6. Ambiente de teste

| Item                | Informação                                 |
| ------------------- | ------------------------------------------ |
| Sistema             | Ingressos Dança e Tradição                 |
| Ambiente            | Produção / Homologação / Local             |
| Navegador principal | Google Chrome                              |
| Navegador adicional | Microsoft Edge                             |
| Sistema operacional | Windows                                    |
| Dispositivo desktop | Notebook/PC                                |
| Dispositivo mobile  | Smartphone ou modo responsivo do DevTools  |
| Banco de dados      | Supabase/PostgreSQL                        |
| Observação          | Utilizar apenas dados fictícios nos testes |

---

## 7. Massa de teste

Os testes devem utilizar compradores fictícios, sem dados pessoais reais.

Exemplo de massa de teste:

| Campo                   | Valor fictício                                            |
| ----------------------- | --------------------------------------------------------- |
| Nome                    | João Teste QA                                             |
| Telefone                | (47) 99999-9999                                           |
| CPF                     | 000.000.000-00                                            |
| E-mail                  | [joao.qa.teste@email.com](mailto:joao.qa.teste@email.com) |
| Assento                 | A10                                                       |
| Forma de pagamento      | Pix manual                                                |
| Status inicial esperado | Reserva pendente de pagamento                             |
| Status após confirmação | Pago / Assento vendido / Ticket gerado                    |

---

## 8. Critérios de entrada

Os testes podem iniciar quando:

* O sistema estiver acessível pelo navegador.
* A página inicial estiver publicada.
* O mapa de assentos estiver disponível.
* Existirem assentos cadastrados no banco.
* O formulário de compra estiver funcional.
* A área administrativa estiver acessível para teste.
* O fluxo de reserva estiver disponível.
* O QA tiver definido a massa de teste.
* O ambiente de teste estiver identificado.

---

## 9. Critérios de saída

O ciclo de testes será considerado finalizado quando:

* Os casos de teste planejados forem executados.
* Os bugs encontrados forem documentados.
* As evidências forem registradas.
* Os fluxos críticos forem validados.
* O relatório final for preenchido.
* Os riscos e limitações forem documentados.
* O status geral do sistema for definido como aprovado, aprovado com ressalvas ou reprovado.

---

## 10. Funcionalidades críticas

As funcionalidades abaixo possuem maior prioridade de validação:

1. Seleção de assento disponível
2. Bloqueio de seleção de assento indisponível
3. Criação de reserva
4. Prevenção de reserva duplicada para o mesmo assento
5. Validação dos dados do comprador
6. Cálculo correto do valor total
7. Confirmação manual de pagamento pelo administrador
8. Alteração do assento para vendido após confirmação
9. Geração de ticket após pagamento
10. Validação de ticket no evento
11. Bloqueio de reuso de ticket já validado

---

## 11. Riscos identificados

| Risco                                           | Impacto                                                |
| ----------------------------------------------- | ------------------------------------------------------ |
| Dois usuários tentarem reservar o mesmo assento | Venda duplicada ou conflito de reserva                 |
| Assento reservado não expirar automaticamente   | Assentos podem ficar presos indevidamente              |
| Dados inválidos no formulário                   | Reserva criada com informações incorretas              |
| CPF exposto em telas ou evidências              | Risco de privacidade                                   |
| Admin confirmar pagamento errado                | Ticket gerado indevidamente                            |
| Ticket validado mais de uma vez                 | Possível entrada duplicada no evento                   |
| QR Code Pix placeholder em produção             | Usuário pode tentar pagar incorretamente               |
| Layout ruim no mobile                           | Usuário pode não conseguir comprar pelo celular        |
| Falha na busca de reservas                      | Admin pode não localizar compradores                   |
| Falha na exportação CSV                         | Organização do evento pode perder controle operacional |

---

## 12. Estratégia de execução

A execução dos testes será feita na seguinte ordem:

1. Smoke test geral do sistema
2. Testes da área pública
3. Testes do fluxo de compra e reserva
4. Testes de validação de formulário
5. Testes de status dos assentos
6. Testes da área administrativa
7. Testes de confirmação de pagamento
8. Testes de geração e validação de ticket
9. Testes mobile
10. Testes exploratórios
11. Testes de regressão
12. Registro de bugs e relatório final

---

## 13. Resultado esperado do ciclo

Ao final do ciclo, espera-se ter uma visão clara sobre a qualidade do sistema, incluindo:

* Funcionalidades aprovadas
* Funcionalidades com falhas
* Bugs encontrados
* Riscos do MVP
* Melhorias recomendadas
* Evidências dos testes
* Conclusão sobre a estabilidade do fluxo principal de compra e validação de ingressos
