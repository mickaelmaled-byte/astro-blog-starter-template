# Regras permanentes — JP Solar Solutions

## 1. A Tindra é a base de tudo
- A Tindra (ERP/CRM, conector MCP «Tindra», empresa JP Solar Solutions, NIF 516651617) é a
  fonte da verdade da empresa: leads, clientes, orçamentos, obras, agenda, faturação.
- **Tudo o que acontece fica registado na Tindra**: cada email de cliente/lead/empreiteiro/
  fornecedor/entidade, cada orçamento, visita, obra iniciada/concluída/registada/certificada.
- Antes de responder sobre um cliente ou obra, ler a Tindra. Depois de qualquer trabalho
  que gere um facto de negócio, registá-lo na Tindra no mesmo turno.
- O que o João Lopes, o Pedro Machado ou o Miguel Almeida põem na Tindra conta: ler o
  histórico e as atividades antes de agir (ex.: saber se o orçamento já foi enviado por eles).
- Skills: `tindra-base` (o quê e quando: regra, emails → Tindra, fecho do dia) e
  `tindra-fluxo-completo` (como escrever: cadeia completa, sem duplicados, confirmações).

## 1-0. Cliente primeiro — ver tudo antes de escrever (regra do Mickael, 18-11-2026)
- Antes de preparar qualquer rascunho, resposta, mensagem de WhatsApp ou proposta para um
  cliente, ler SEMPRE: (1) a Tindra — lead/obra, notas, histórico, atividades e o que o
  João/Pedro/Miguel registaram; (2) todo o histórico de emails com esse cliente (recebidos
  e enviados, incluindo os que a geral@ pôs em cópia); (3) a memória SOLENERGE, se for o
  caso; (4) as sessões anteriores do Claude sobre esse cliente, se houver rascunhos ou
  promessas pendentes (list_sessions / list_events).
- Nada fica pendurado: rascunhos e emails por preparar vão ao revisor (secção 1-C); as
  dúvidas sobre cada um perguntam-se ao Mickael com opções.

## 1-A. Propostas ligadas à lead (desde 17-11-2026)
- Cada proposta/orçamento enviado passa a ter o orçamento (OR) em rascunho ligado à lead
  na Tindra: produtos (linhas) na lead → `crm_oportunidade_criar_orcamento` (exige
  cliente; se faltar, `crm_oportunidade_criar_cliente`). Nota com o nome do PDF e a data.
- Se o Mickael e o João enviarem valores diferentes ao mesmo cliente, fica sempre o
  VALOR MAIS BAIXO.
- Exceção: SOLENERGE (ver secção 1-B).

## 1-B. SOLENERGE — fora da Tindra, prioridade máxima
- Os processos SOLENERGE (Açores, DREn) NÃO se registam na Tindra.
- Emails SOLENERGE têm prioridade: preparar sempre o rascunho de resposta no Outlook
  (o envio só pelo circuito do revisor, secção 1-C), preparar os documentos em falta,
  avisar do que é preciso assinar e dizer quando o rascunho está pronto.
- Estado de cada processo na memória `.claude/memoria/solenerge-processos.md`.
- Skill: `solenerge-acompanhamento`.

## 1-C. Rascunhos: revisão e envio
- Todo o rascunho de email passa pelo agente `revisor-rascunhos` (skill
  `revisao-rascunhos`): APROVADO → o revisor envia; CORRIGIR → o agente principal corrige
  e volta a submeter; BLOQUEADO (assinatura, facto por confirmar, decisão) → pergunta ao
  Mickael. Nunca enviar rascunhos que o Mickael mandou segurar.
- Depois de enviar, pôr a categoria «Respondido» no email original recebido.

## 2. Fecho do dia
- Dias úteis ao fim da tarde: ler na Tindra as obras, instalações, visitas e atividades
  do dia, os emails ainda não registados, e fazer ao Mickael perguntas numeradas para
  fechar tudo (concluída → `concluir`; registada → `legalizar`; certificada → `fechar`;
  reagendar; próximo passo). Detalhe na skill `tindra-base`.

## 2-A. Lembrete 24 horas antes
- Todos os dias úteis às 09:13 (Lisboa) a tarefa agendada «Lembrete 24 h — tarefas de
  amanhã» lê na Tindra as marcações, obras e atividades do dia seguinte (à sexta: sábado
  a segunda), aponta conflitos e dados em falta e pergunta se é preciso alterar algo.

## 2-B. Regras de agenda e perguntas
- A JP NÃO faz visitas técnicas ao sábado (regra do Mickael, 18-11-2026). Propor sempre
  dias úteis; se o cliente pedir fim de semana, propor o fim do dia num dia útil.
- Perguntas ao Mickael: sempre com opções para escolher (ferramenta de perguntas com
  opções), nunca só em texto no meio da mensagem.

## 2-C. WhatsApp
- Não há ligação direta ao WhatsApp. Quando o Mickael pedir «responde por WhatsApp a X»:
  1) ler o contacto e o histórico na Tindra/Outlook; 2) escrever a mensagem no padrão JP
  (curta, «Bom dia/Boa tarde», valores em *negrito*, sem câmbio/USD nem outros clientes);
  3) dar o link pronto a enviar https://wa.me/<número sem +>?text=<mensagem codificada>
  e dizer que PDF juntar; 4) depois de ele confirmar o envio, registar na Tindra (nota,
  etapa, próxima atividade) e apagar rascunhos de email equivalentes, se ele aprovar.

## 3. Limites
- Estados de obra, ganhar/perder leads, faturação e comandos ⚠️ IRREVERSÍVEIS: confirmar
  primeiro. Lead nova, dados de contacto, notas e atividades: fazer logo.
- Nunca inventar NIF, valores, datas ou clientes.
