---
name: tindra-base
description: "A Tindra é a BASE DE TUDO na JP Solar Solutions: CRM, obras, agenda, orçamentos, faturação. Esta skill define a regra «Tindra primeiro», o registo automático de cada email que entra (leads, pedidos de orçamento, respostas de clientes; os SOLENERGE seguem à parte na skill solenerge-acompanhamento) e o FECHO DO DIA: ao fim da tarde lê as obras, instalações, visitas e atividades agendadas na Tindra e faz ao Mickael as perguntas para as fechar (concluída, registada, certificada, reagendar...). Disparar com: «fecho do dia», «o que ficou do dia», «revê a agenda», «passa os emails para a Tindra», «regista os emails», «o que temos amanhã», «que obras estão por fechar», «a obra X acabou / está registada / está certificada», qualquer email de cliente ou fornecedor que chegue, e sempre que uma conversa produza um facto de negócio (orçamento feito, visita marcada, cliente aceitou, obra concluída). Para EXECUTAR as escritas usa a skill tindra-fluxo-completo."
---

# Tindra primeiro — base de tudo da JP Solar

**Versão 2026-11-17 (rev. 2).** Regra n.º 1, acima de qualquer outra: **se aconteceu, tem de estar
na Tindra.** Um email, um orçamento, uma visita, uma obra acabada, um registo na DGEG/DREn
— nada fica só no Outlook, no SharePoint, no WhatsApp ou na conversa.

As escritas fazem-se sempre pelas regras da skill **tindra-fluxo-completo** (ler antes de
escrever, não duplicar, comandos de negócio, `chave_idempotencia`, `versao_esperada`,
verificar no fim). Esta skill diz **o quê e quando**; a outra diz **como**.

## 1. Regra «Tindra primeiro» (em qualquer conversa)

1. **Antes de responder sobre um cliente, obra ou orçamento**, lê a Tindra
   (`pesquisar_tudo` → `ler_registo`). A Tindra é a fonte da verdade; o resto é apoio.
2. **Depois de qualquer trabalho que gere um facto de negócio**, regista-o na Tindra no
   mesmo turno (orçamento feito → linhas na lead + **OR em rascunho ligado** com
   `crm_oportunidade_criar_orcamento` + nota com o PDF + etapa `orcamento_enviado`; visita marcada →
   `crm_oportunidade_agendar_visita`; obra acabou → `obras.obra.concluir`; etc.).
3. **Nenhuma lead ou obra em aberto fica sem próximo passo** (atividade com prazo e
   responsável).
4. O que João Lopes, Pedro Machado ou Miguel Almeida registarem na Tindra é tão válido
   como o que tu registas: **lê sempre o histórico e as atividades deles** antes de agir
   (ex.: «o Pedro já enviou o orçamento?» → ver OR/proposta ligada e histórico da lead).

### Quem faz o orçamento — leitura da Tindra
Para «temos de fazer orçamento?», «já foi enviado?», «quem faz?»:
- Lead em `contacto`/`visita_tecnica` sem OR ligado e sem linhas → **orçamento por fazer**.
  Responsável = comercial da lead (atividade «Enviar orçamento»).
- OR ligado em rascunho → **feito, por enviar**. OR emitido/proposta enviada ou etapa
  `orcamento_enviado` → **enviado** (por quem: ver histórico/autor).
- `negociacao` → à espera de decisão; `adjudicado` (ganha) → nasce a obra.

### Valores em conflito
Se o Mickael e o João enviarem propostas diferentes ao mesmo cliente, fica na Tindra o
**valor mais baixo** (regra do Mickael, 17-11-2026).

### Exceção SOLENERGE
Processos SOLENERGE ficam FORA da Tindra — ver skill `solenerge-acompanhamento`.

## 2. Emails → Tindra (cada email que entra)

Fontes: caixa do Mickael e `geral@` (Outlook, `outlook_email_search` + `read_resource`).
Para cada email novo de **cliente, lead, empreiteiro, fornecedor ou entidade (SOLENERGE,
DREn, DGEG, EDA, E-Redes)** — ignora newsletters, publicidade e emails automáticos:

| O email é… | Registo na Tindra |
|---|---|
| Pedido de contacto / orçamento novo | F1: procura repetidos; se não houver, cria a lead no CRM certo com tudo o que o email traz (nome, telemóvel, email, morada, CP, consumo, interesse) + atividade «Contactar» ao Mickael (Nuno no Douro Sul) |
| Resposta de cliente com dados (telefone, morada, fatura, fotos) | Atualiza a lead/obra com os dados novos (só campos vazios ou errados) e conclui/reagenda a atividade pendente com o resumo |
| Cliente aceita / adjudica | F4 (marcar ganha → obra). **Confirma comigo antes** |
| Cliente aceita dia e hora de visita | F2: `crm_oportunidade_agendar_visita` (ou atualizar a marcação existente) |
| Empreiteiro pede cotação / insiste | Lead (ou atualizar a existente) + atividade com prazo curto e prioridade |
| Qualquer email SOLENERGE / DREn / registo UPAC Açores | **NÃO vai para a Tindra.** Tratar PRIMEIRO com a skill `solenerge-acompanhamento` (rascunho de resposta, documentos, memória própria) |
| Fatura de fornecedor | `compras_carregar_fatura_fornecedor` em rascunho, ligada à obra |
| Desistência | F8: perdida com motivo. **Confirma comigo antes** |

Regras do registo de emails:
- **Sem duplicados:** procura por email do remetente, telemóvel e nome antes de criar.
- No histórico/nota escreve: data, remetente, assunto e um resumo de 1–3 linhas.
- Escritas simples (lead nova sem repetidos, dados de contacto, notas, atividades) fazem-se
  **logo, sem perguntar**. Mudanças de etapa ganha/perdida, estados de obra, faturação e
  tudo o que seja ⚠️ IRREVERSÍVEL **pedem confirmação**.
- No fim, uma lista curta: «Registei X emails: … | Precisa de decisão: …».

## 3. Fecho do dia (fim da tarde, dias úteis)

Corre `date` primeiro. Fuso da empresa: Atlantic/Azores; as obras do Continente usam
Europe/Lisbon — mostra as horas no fuso da obra.

**Recolha (só leitura):**
0. SOLENERGE primeiro: skill `solenerge-acompanhamento` (emails novos, memória, rascunhos, assinaturas).
1. `resumo` — atividades atrasadas/hoje/planeadas.
2. `agenda.marcacao` com início hoje (e amanhã, para preparar): instalações, visitas,
   reuniões — com obra/lead ligada e participantes.
3. `obras.obra` em `agendada` ou `em_curso` com `data_prevista_inicio`/`fim` ≤ hoje;
   em `concluida` (falta legalizar) e em `legalizacao_dgeg` (falta certificar/fechar).
4. `crm.oportunidade` com visita hoje, ou em `orcamento_enviado`/`negociacao` há > 7 dias
   sem atividade.
5. `nucleo.atividade` pendentes com prazo ≤ hoje, do Mickael e da equipa.
6. Emails do dia ainda não registados (secção 2).

**Perguntas ao Mickael** — numeradas, curtas, agrupadas, com resposta rápida possível:

```
FECHO DO DIA — ter 17-11
Obras/instalações de hoje
 1. OB-2026-00xx Isabel (Coval) — instalação 2/2 hoje. Concluída? (sim / falta X / reagendar p/ dd)
Visitas de hoje
 2. Visita Paulo Vieira — feita? Próximo passo: orçamento por nós ou já enviado?
Legalização
 3. OB-2026-0011 Costa Nova — concluída a 16-11. Registo DGEG já submetido? (→ «registada»)
Atividades atrasadas (5)
 4. «Ligar ao Nuno Cabrita» — feito? resultado?
Buracos na Tindra
 5. Instalação 17–18/11 (Miguel + Mickael) sem obra nem lead — de que cliente é?
Emails por decidir
 6. GJSilva insiste na cotação — fazemos hoje ou amanhã?
Amanhã: 2 visitas, 1 instalação (lista)
```

**Tradução das respostas para a Tindra** (executar pela tindra-fluxo-completo):

| Resposta | Ação |
|---|---|
| «começou» / «está em curso» | `obras.obra.iniciar` (+ `data_inicio`) |
| «concluída» / «acabou» | `obras.obra.concluir` (+ `data_conclusao`); se faltarem checklist, n.ºs de série ou auto de entrega, cria atividades para isso |
| «registada» (registo DGEG/DREn/SOLENERGE submetido) | `obras.obra.legalizar` + nota com n.º de registo/processo + atividade «Acompanhar certificado» |
| «certificada» (certificado/registo aprovado) | anexar prova, conferir saldo por faturar/receber e `obras.obra.fechar` (se houver saldo, perguntar) |
| «reagendar para dd» | `agenda.marcacao.atualizar` / `obras.obra.atualizar` datas — nunca criar marcação nova |
| «visita feita, orçamento por nós» | concluir atividade da visita + atividade «Enviar orçamento» (prazo 2 dias úteis) |
| «o Pedro/João já enviou» | confirmar OR/proposta ligado; etapa `orcamento_enviado` + atividade de seguimento |
| «feito» numa atividade | `nucleo_atividade_concluir` com o resultado em `feedback` + próxima atividade se fizer sentido |
| «perdemos» | F8 com motivo |

Estados válidos da obra: planeamento → agendada → em_curso → concluida → legalizacao_dgeg →
fechada. Não saltar estados (só um gestor recua).

No fim do fecho: relatório de 5–10 linhas — o que mudou (com códigos OB/OR), o que ficou
pendente e o plano de amanhã.

## 4. Higiene que se corrige sempre que se vê
- Marcações de instalação **sem obra** → ligar à obra (ou à lead, se ainda não ganha).
- Leads com instalação marcada mas ainda em `contacto`/`orcamento_enviado` → perguntar se
  foram adjudicadas (F4) para nascer a obra.
- Obras sem orçamento (`orcamento_centimos`), sem morada/CP ou sem responsável.
- Obras com data prevista passada e ainda em `planeamento`/`agendada`.
- Atividades atribuídas a quem não as faz (os contactos às leads são do Mickael/Nuno).
