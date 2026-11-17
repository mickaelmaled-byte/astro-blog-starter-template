---
name: solenerge-acompanhamento
description: "Acompanhamento PRIORITÁRIO dos processos SOLENERGE (Açores, DREn / Direção Regional da Energia) da JP Solar Solutions, FORA da Tindra. Sempre que chega um email SOLENERGE (remetente @azores.gov.pt, assunto com «SOLENERGE» ou um n.º de processo, ou um cliente SOLENERGE a enviar documentos), trata-o PRIMEIRO: lê, atualiza a memória dos processos, prepara o rascunho de resposta no Outlook (nunca envia), prepara os documentos em falta com as skills SOLENERGE, avisa o Mickael do que é preciso assinar e diz-lhe quando o rascunho está pronto a enviar. Disparar com: «SOLENERGE», «Solenergy», «DREn», «Portal da Energia», «processo 29xxx/30xxx», «como estão os processos», «o que falta à SOLENERGE», «pedido de esclarecimento», «fase 2», «fase 3», «recibo», «consignação», e em cada revisão de emails ou fecho do dia."
---

# SOLENERGE — acompanhamento prioritário (fora da Tindra)

**Versão 2026-11-17. Regras do Mickael:**
1. **Os processos SOLENERGE NÃO vão para a Tindra.** Não criar leads, obras, notas,
   atividades nem processos de apoio na Tindra para SOLENERGE. Seguem «à parte».
2. **Prioridade máxima.** Em qualquer revisão de emails, os SOLENERGE vêm primeiro.
3. **Preparar sempre a resposta**, em rascunho no Outlook do Mickael
   (`outlook_create_reply_draft` / `outlook_create_reply_all_draft` /
   `outlook_create_draft`). **Nunca enviar.** No fim, dizer: «Rascunho pronto para
   enviares: <assunto> → <destinatário>».
4. **Se faltar documentação** para responder: preparar o que for possível (PDFs com as
   skills abaixo), deixar o rascunho pronto e dizer exatamente o que falta e quem o dá.
5. **Assinaturas:** se algum documento tiver de ser assinado (pelo Mickael, pelo gerente
   João Lopes ou pelo cliente), avisar SEMPRE e logo, antes do rascunho final.
6. **Memória interna:** manter o estado de cada processo em
   `.claude/memoria/solenerge-processos.md` (ver formato abaixo). Atualizar a cada email.
7. **Informar sempre** o ponto de situação: o que recebemos, o que a DREn precisa, o que
   temos de preparar, prazos.

## Fluxo para cada email SOLENERGE

1. **Identificar o processo** (n.º no assunto/corpo, email do cliente, nome) e ler a
   entrada na memória. Se não existir, criar.
2. **Ler o email todo e os anexos** (`read_resource`). Nunca copiar para a memória
   palavras-passe ou credenciais que clientes enviem — escrever só «credenciais
   recebidas por email em dd/mm (não guardadas)».
3. **Classificar o pedido** e escolher a skill:

| Pedido | Skill / ação |
|---|---|
| Parecer + Termo de aceitação → contrato | `consignacao-solenerge` (contrato, Declaração de Veracidade Anexo IV, email ao cliente) |
| Fase 2 (submissão) / listas / declarações | `submissao-fase-2-solenerge` (SNs das fotos, 4 PDFs oficiais, verificação dos 12+ documentos) |
| Registo da UPAC no Portal da Energia (MCP) | `certificacao-upac-acores` e `registo-mcp-upac` (unifilar, termo de responsabilidade, declaração de limitação, campos do formulário) |
| Pedido de esclarecimento da DREn (fotos, faturas EDA, certidões...) | reunir o que pediram; se o cliente tem de enviar, preparar email ao cliente; preparar resposta à DREn |
| Fase 3 (recibos RC, comprovativos, extrato) | preparar resposta; se o cliente pede que a JP submeta, indicar o que é preciso |

4. **Preparar os rascunhos** (à DREn e/ou ao cliente), com anexos se existirem.
   Assinar como «Mickael Antunes — JP Solar Solutions».
5. **Atualizar a memória** do processo: fase, último recebido/enviado, o que falta,
   prazos, assinaturas pendentes, rascunhos prontos.
6. **Relatório ao Mickael** (curto, sempre por esta ordem):
   - ⚠️ Para assinar: …
   - 📎 Falta (quem): …
   - ⏰ Prazos: …
   - ✉️ Rascunhos prontos para enviares: …

## Prazos
- «10 dias úteis» conta-se a partir da data do email da DREn, sem sábados, domingos e
  feriados (nacionais + Açores). Escrever sempre a data concreta.
- URGENTE = prazo ≤ 5 dias úteis, ou pedido da DREn sem resposta há > 2 dias úteis.

## Formato da memória (`.claude/memoria/solenerge-processos.md`)

```
## <n.º processo> — <cliente> (<ilha/concelho>)
- Contactos: cliente <email/tel>; DREn <pessoa/email>
- Fase: <candidatura | consignação | instalação | fase 2 | registo UPAC | esclarecimento | fase 3 | pago>
- Último recebido: <dd/mm> <de quem> — <o quê>
- Último enviado: <dd/mm> — <o quê>
- Falta: <item> (quem: JP/cliente/DREn) …
- Prazo: <data> — <o quê>
- Assinaturas pendentes: <documento> (quem)
- Rascunhos prontos: <assunto> (dd/mm)
- Notas: <ID registo, RC n.º, etc.>
```

No topo do ficheiro: «Atualizado em <data hora>» e a lista **Próximas ações por
prioridade**.

## Revisões automáticas
- Em cada revisão de emails, no fecho do dia e sempre que o Mickael perguntar «como estão
  os processos», abrir a memória, procurar emails SOLENERGE novos desde a última
  atualização, tratar cada um pelo fluxo acima e devolver o relatório.
