---
name: revisao-rascunhos
description: "Circuito de revisão e envio dos rascunhos de email do Mickael (JP Solar Solutions): o agente revisor-rascunhos avalia cada rascunho (destinatários, anexos, valores, português, regras JP, SOLENERGE), o agente principal corrige o que ele apontar, o revisor volta a avaliar e só envia os aprovados. Disparar com: «revê os rascunhos», «vê se os emails estão prontos», «envia os rascunhos que estiverem bem», «podemos enviar?», e no fim de cada preparação de rascunhos (SOLENERGE, propostas, respostas a clientes)."
---

# Revisão e envio de rascunhos

**Versão 2026-11-17.** Autorização do Mickael: o revisor pode ENVIAR os rascunhos que
aprovar. Tudo o resto volta para correção.

## Circuito (máximo 3 rondas por rascunho)
1. Lançar o agente `revisor-rascunhos` (Agent tool, subagent_type «revisor-rascunhos»;
   se não existir esse tipo, usar general-purpose com o conteúdo de
   `.claude/agents/revisor-rascunhos.md` como instruções) com o modo e a lista de
   rascunhos. **Não lhe dar a nossa opinião sobre os rascunhos** — revisão independente.
2. Para cada CORRIGIR: corrigir o rascunho no Outlook (`outlook_update_draft`; anexos em
   falta com o ficheiro certo; se for preciso gerar um PDF, usar a skill própria) e
   voltar ao passo 1 só com esses rascunhos.
3. BLOQUEADO (assinatura, facto por confirmar, decisão): não mexer; perguntar ao Mickael
   numa só mensagem.
4. Após 3 rondas sem aprovação → passa a BLOQUEADO.
5. Envio: o revisor envia os APROVADOS (modo «enviar»).
6. **Depois do envio:**
   - não SOLENERGE → registar na Tindra (skill tindra-base: nota no histórico, etapa,
     OR ligado à lead, próxima atividade);
   - SOLENERGE → atualizar `.claude/memoria/solenerge-processos.md` (último enviado,
     rascunhos prontos = nenhum, próximo prazo).
7. Relatório ao Mickael: ✅ Enviados · 🔧 Corrigidos e enviados · ⛔ À tua espera (porquê).

## Modo
- Por omissão o revisor corre em modo «enviar» quando o Mickael pediu para enviar os
  que estiverem bem; caso contrário, «rever».
- Nunca enviar um rascunho que o Mickael tenha dito para segurar.
