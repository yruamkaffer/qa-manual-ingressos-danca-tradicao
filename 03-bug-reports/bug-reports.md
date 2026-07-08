# Bug Reports — Ingressos Dança e Tradição

## Resumo

Durante a execução dos casos de teste funcionais, foram identificados dois bugs visuais no sistema **Ingressos Dança e Tradição**.

Os bugs encontrados não impedem totalmente o uso do sistema, porém impactam a experiência visual, a clareza das informações e a qualidade percebida pelo usuário/admin.

---

# BUG-001 — Texto da barra de busca sobreposto ao ícone no painel administrativo

## Identificação

**ID:** BUG-001
**Funcionalidade:** Área administrativa / Reservas
**Tipo:** Visual / Interface
**Severidade:** Baixa
**Prioridade:** Média
**Status:** Aberto
**Relacionado ao caso de teste:** CT-009 — Localizar reserva no painel administrativo

---

## Ambiente

| Item                | Informação     |
| ------------------- | -------------- |
| Ambiente            | Homologação    |
| Navegador           | Microsoft Edge |
| Sistema operacional | Windows 10     |
| Dispositivo         | Desktop        |
| Data                | 08/07/2026     |
| Responsável         | Yruam Käffer   |

---

## Pré-condição

O usuário administrador deve estar autenticado e com acesso ao painel administrativo.

---

## Passos para reproduzir

1. Acessar o sistema em ambiente de homologação.
2. Realizar login na área administrativa.
3. Acessar a aba **Reservas**.
4. Observar o campo de busca localizado no painel de reservas e pedidos.

---

## Resultado esperado

O campo de busca deve exibir o ícone e o texto placeholder de forma clara, alinhada e sem sobreposição visual.

---

## Resultado atual

O texto do placeholder da barra de busca aparece sobreposto ou muito próximo ao ícone, prejudicando a legibilidade e o acabamento visual do componente.

---

## Evidência

`05-evidencias/bugs/BUG-001.png`

---

## Impacto

O bug não impede a busca de reservas, mas prejudica a experiência visual do administrador e passa a impressão de falta de acabamento na interface.

---

## Sugestão de correção

Ajustar o espaçamento interno do campo de busca, adicionando padding à esquerda ou reposicionando o ícone para evitar sobreposição com o placeholder.

Exemplo de abordagem:

* aumentar `padding-left` do input;
* garantir alinhamento vertical do ícone;
* validar o componente em diferentes larguras de tela.

---

# BUG-002 — Sobreposição de textos no ticket/PDF gerado

## Identificação

**ID:** BUG-002
**Funcionalidade:** Ticket / PDF do ingresso
**Tipo:** Visual / Layout
**Severidade:** Média
**Prioridade:** Alta
**Status:** Aberto
**Relacionado ao caso de teste:** CT-011 — Validar geração de ticket com QR Code

---

## Ambiente

| Item                | Informação     |
| ------------------- | -------------- |
| Ambiente            | Homologação    |
| Navegador           | Microsoft Edge |
| Sistema operacional | Windows 10     |
| Dispositivo         | Desktop        |
| Data                | 08/07/2026     |
| Responsável         | Yruam Käffer   |

---

## Pré-condição

Deve existir uma reserva com pagamento confirmado e ticket gerado pelo sistema.

---

## Passos para reproduzir

1. Criar uma reserva com dados válidos.
2. Confirmar manualmente o pagamento na área administrativa.
3. Gerar ou acessar o ticket/PDF do ingresso.
4. Observar o cabeçalho do ticket, especialmente as informações de local e cidade.

---

## Resultado esperado

O ticket deve exibir todas as informações do evento de forma clara, organizada e sem sobreposição de textos.

---

## Resultado atual

No ticket/PDF gerado, há sobreposição entre textos no cabeçalho, confundindo a leitura das informações de local/cidade do evento.

---

## Evidência

`05-evidencias/bugs/BUG-002.png`

---

## Impacto

O bug afeta a clareza visual do ticket enviado ao comprador. Como o ticket é o documento final utilizado pelo participante no dia do evento, a sobreposição pode causar confusão e prejudicar a percepção de qualidade do sistema.

---

## Sugestão de correção

Revisar o layout do cabeçalho do ticket/PDF, ajustando espaçamentos, altura dos blocos e quebra de linha das informações do evento.

Possíveis correções:

* aumentar a altura da área do cabeçalho;
* separar local e cidade em linhas distintas;
* revisar margens entre título, data, horário, teatro e cidade;
* validar o PDF após geração em diferentes tamanhos de tela;
* garantir que elementos absolutos não estejam se sobrepondo ao conteúdo textual.

---

# Resumo dos bugs encontrados

| ID      | Resumo                                                               | Severidade | Prioridade | Status |
| ------- | -------------------------------------------------------------------- | ---------- | ---------- | ------ |
| BUG-001 | Texto da barra de busca sobreposto ao ícone no painel administrativo | Baixa      | Média      | Aberto |
| BUG-002 | Sobreposição de textos no ticket/PDF gerado                          | Média      | Alta       | Aberto |

---
