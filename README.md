# QA Manual — Ingressos Dança e Tradição

## Sobre o case

Este repositório reúne a documentação de QA Manual aplicada ao sistema **Ingressos Dança e Tradição**, um MVP web para reserva e venda de ingressos de espetáculo de dança.

O sistema permite que o comprador escolha o tipo de ingresso, selecione a quantidade desejada, preencha seus dados, realize o pagamento manual via Pix e envie o comprovante pelo WhatsApp. Após a confirmação manual pelo administrador, o sistema gera o ticket final com QR Code para validação na entrada do evento.

Este case foi criado com o objetivo de demonstrar, na prática, conhecimentos de QA Manual, documentação de testes, análise de requisitos, critérios de aceite, casos de teste, bug reports, checklists, evidências e relatório final.

---

## Sistema testado

**Nome do projeto:** Dança & Tradição Tickets
**Tipo de sistema:** MVP web para venda e reserva de ingressos
**Repositório do sistema:** IngressosDancaeTradicao
**Área de aplicação:** Eventos / Espetáculos / Venda de ingressos
**Fluxo principal:** Compra de ingresso + confirmação manual + geração de ticket com QR Code

---

## Tecnologias do sistema

O sistema testado foi desenvolvido com:

* Next.js
* React
* TypeScript
* Supabase
* PostgreSQL
* Tailwind CSS
* Vercel
* QR Code para tickets
* Fluxo manual de pagamento via Pix/WhatsApp

---

## Objetivo dos testes

Validar manualmente as principais funcionalidades do sistema, garantindo que o fluxo de compra, reserva, pagamento manual, confirmação administrativa e validação de tickets funcione corretamente.

O foco deste case é avaliar:

* clareza do fluxo para o usuário;
* validação dos dados do comprador;
* cálculo correto dos valores;
* criação correta das reservas;
* funcionamento do pagamento manual;
* confirmação administrativa;
* geração de tickets com QR Code;
* validação de tickets na entrada;
* controle de capacidade interna;
* experiência em desktop e mobile;
* possíveis riscos e melhorias do MVP.

---

## Escopo do case de QA

Este case contempla testes manuais nas seguintes áreas:

### Área pública

* Landing page do evento
* Informações do espetáculo
* Escolha do tipo de ingresso
* Seleção da quantidade
* Formulário do comprador
* Validação de campos obrigatórios
* Validação de CPF
* Cálculo do valor total
* Criação de reserva
* Tela de pagamento Pix
* Instruções de envio de comprovante via WhatsApp
* Página de ticket após confirmação
* Exibição do QR Code do ticket
* Responsividade mobile

### Área administrativa

* Acesso administrativo
* Dashboard admin
* Busca de reservas
* Confirmação manual de pagamento
* Cancelamento de reserva
* Geração de cortesia
* Exportação CSV
* Validação de ticket
* Controle de ticket já utilizado
* Controle interno de capacidade do evento

### Regras de negócio

* Tipos de ingresso: inteira, meia/promocional e cortesia
* Quantidade de ingressos por compra
* Limite máximo de ingressos por pedido
* Capacidade interna de 640 lugares
* Prevenção de venda acima da capacidade disponível
* Geração de ticket somente após confirmação do pagamento
* Geração de cortesia apenas pela área administrativa
* Ticket cortesia com valor zero
* Validação única do QR Code do ticket

---

## Fora do escopo

Neste primeiro ciclo de testes, não serão contemplados:

* testes automatizados;
* testes de carga;
* testes de segurança avançada;
* testes com Pix real;
* integração com gateway de pagamento;
* auditoria completa do banco de dados;
* testes em todos os navegadores existentes;
* validação com dados pessoais reais;
* escolha pública de assentos numerados;
* mapa público de assentos.

---

## Tipos de teste aplicados

* Smoke test
* Teste funcional
* Teste exploratório
* Teste de regressão
* Teste responsivo
* Teste de interface
* Teste de validação de formulário
* Teste de regra de negócio
* Teste de QR Code
* Teste administrativo

---

## Estrutura do repositório

```bash
qa-manual-ingressos-danca-tradicao/
│
├── README.md
│
├── 01-plano-de-teste/
│   └── plano-de-teste.md
│
├── 02-casos-de-teste/
│   └── casos-de-teste.md
│
├── 03-bug-reports/
│   └── bug-reports.md
│
├── 04-checklists/
│   ├── smoke-test.md
│   └── admin.md
│
├── 05-evidencias/
│   ├── casos-de-teste/
│   ├── smoke-test/
│   ├── bugs/
│   └── README.md
│
├── 06-relatorio-final/
│   └── relatorio-final.md
│
└── 07-linkedin/
    └── post-linkedin.md
```

---

## Documentos do case

| Documento              | Objetivo                                               | Status       |
| ---------------------- | ------------------------------------------------------ | ------------ |
| Plano de Teste         | Definir escopo, ambiente, riscos e estratégia de teste | Feito        |
| Casos de Teste         | Documentar os cenários e passos de validação           | Feito        |
| Bug Reports            | Registrar falhas encontradas durante os testes         | Feito        |
| Smoke Test             | Validar rapidamente se o sistema está funcional        | Feito        |
| Checklist de Regressão | Garantir que funcionalidades antigas não quebrem       | Feito        |
| Checklist Mobile       | Validar comportamento em telas menores                 | Feito        |
| Checklist Admin        | Validar fluxos administrativos                         | Feito        |
| Evidências             | Armazenar prints e registros dos testes                | Feito        |
| Relatório Final        | Consolidar resultados do ciclo de QA                   | Feito        |
| Post LinkedIn          | Apresentar o case de QA Manual publicamente            | Feito        |

---

## Funcionalidades críticas

As funcionalidades mais importantes para validação são:

1. Carregamento da landing page
2. Escolha do tipo de ingresso
3. Seleção da quantidade
4. Bloqueio de quantidade inválida
5. Validação dos dados obrigatórios
6. Validação de CPF inválido
7. Cálculo correto do valor total
8. Criação de reserva pendente de pagamento
9. Exibição da tela de pagamento Pix
10. Instrução clara de envio do comprovante pelo WhatsApp
11. Confirmação manual pelo administrador
12. Geração de ticket com QR Code
13. Validação de ticket na entrada
14. Bloqueio de revalidação do mesmo ticket
15. Geração de cortesia administrativa
16. Exportação CSV de pedidos pagos
17. Controle interno de capacidade
18. Responsividade no mobile

---

## Massa de teste

Os testes serão realizados apenas com dados fictícios.

Exemplo:

| Campo                   | Valor                                                     |
| ----------------------- | --------------------------------------------------------- |
| Nome                    | João Teste QA                                             |
| Telefone                | (47) 99999-9999                                           |
| CPF                     | 000.000.000-00                                            |
| E-mail                  | [joao.qa.teste@email.com](mailto:joao.qa.teste@email.com) |
| Tipo de ingresso        | Inteira / Meia / Cortesia                                 |
| Quantidade              | 1 a 10                                                    |
| Forma de pagamento      | Pix manual                                                |
| Status inicial          | Pendente de pagamento                                     |
| Status após confirmação | Pago                                                      |
| Ticket                  | Gerado com QR Code                                        |

---

## Riscos observados no MVP

Durante a análise inicial do sistema, foram identificados alguns pontos de atenção para validação:

* venda acima da capacidade disponível;
* reserva pendente sem expiração automática;
* cálculo incorreto de valor total;
* QR Code Pix incorreto ou placeholder em produção;
* confirmação administrativa indevida;
* ticket validado mais de uma vez;
* exposição desnecessária de CPF;
* cortesia gerada sem controle adequado;
* falha no mobile;
* CSV com dados incompletos ou incorretos;
* inconsistência entre status da reserva e status do ticket.

---

## Objetivo profissional do case

Este projeto faz parte da minha transição de carreira para a área de tecnologia, com foco inicial em **QA Manual**.

A proposta é demonstrar minha capacidade de:

* entender um sistema real;
* analisar regras de negócio;
* planejar testes;
* documentar casos de teste;
* registrar bugs com clareza;
* validar fluxos críticos;
* pensar em riscos;
* organizar evidências;
* comunicar resultados de forma profissional.

