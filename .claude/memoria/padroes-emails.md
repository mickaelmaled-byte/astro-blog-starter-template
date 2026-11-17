# Padrões dos emails do Mickael — guia para o revisor de rascunhos

Fonte: Itens Enviados de mickael.antunes@jpsolarsolutions.pt, 17/09/2026 a 17/11/2026 (223 emails;
~52 lidos na íntegra, os restantes pelo resumo). Marcadores: <cliente>, <n.º>, <valor>, <data>, <local>.

## (a) Regras gerais de estilo e assinatura

- Português de Portugal, AO90 («atual», «elétrico», «proteções»; nunca «actualmente», «eléctrico», «protecções»).
- Tom cordial e profissional, frases curtas, listas com marcadores para equipamento, documentos e pedidos.
  Tratar o cliente na 3.ª pessoa («o senhor», «indique-nos»). Nunca usar ironia ou responder com irritação.
- Saudação: `Bom dia, Sr. <Nome Apelido>,` / `Boa tarde, D. <Nome>,`. Usar o nome tal como o cliente assina,
  com acentos («Lídia», não «Lidia»). Não misturar «Caro» com «Bom dia» («Bom dia, Caro Erik» está errado).
  Hora de Lisboa no momento do envio: até às 12h59 «Bom dia», a partir das 13h00 «Boa tarde». Se o rascunho
  foi feito de manhã e só sai à tarde, corrigir.
- Entidades: `Exmos. Senhores,` (caixa genérica) ou `Exmo. Senhor <Nome>,` / `Exma. Sra. Dra. <Nome>,`;
  Eng. quando o técnico assina como engenheiro (ex.: `Exmo. Senhor Eng. <Nome>,`).
- Internos: `Olá João,` / `João,` / `Bom dia João / Pedro,` (trato por «tu»).
- Fecho padrão antes da assinatura: «Ficamos ao dispor para qualquer esclarecimento.» (DREn: «… esclarecimento adicional.»).
- Bloco de assinatura (texto exato, obrigatório em tudo o que sai para fora):

```
Com os melhores cumprimentos,
Mickael Antunes

🏛️ JP Solar Solutions Lda / Solceller Lda
📠 928 063 925
📑 NIPC: 516651617
https://www.solceller.pt/
```
  Uma só vez (já saiu «Com os melhores cumprimentos,» duplicado). Nunca terminar só com «Com os melhores
  cumprimentos,» sem nome. A assinatura do João (geral@, com morada fiscal e armazém) não é a do Mickael.
- Valores: separador de milhares com espaço e vírgula decimal: `6 621,18 €` (não `6.621,18 €`).
  Particulares: `<valor> € sem IVA (<valor> € com IVA)` ou `<valor> € + IVA (<valor> € com IVA a 23%)`, em negrito.
  Confirmar que valor × 1,23 = valor com IVA e que os valores do email = valores do PDF.
- «Proposta prévia»: dizer sempre que o orçamento final só fica fechado depois da fatura e da visita técnica
  (gratuita na zona) ou da videochamada gratuita (zonas longe: Algarve, Minho, Lisboa, Viana).
- Responder sempre na mesma conversa (RE:) quando há email anterior; não abrir conversa nova.
- Nunca deixar marcadores de rascunho: `[CONFIRMAR…]`, `<…>`, `XX`, «ex.:» com datas inventadas.

## (b) Padrões por tipo

### 1. Proposta / orçamento UPAC a particular (o tipo mais frequente, ~35%)
- Assunto: resposta mantém o original (`RE: Pedido de Orçamento #<n.º> - "🏠 Autoconsumo / UPAC (residencial)"`,
  `RE: Pedido de orçamento — <descrição>`); novo: `Proposta de sistema fotovoltaico com bateria – <localidade>`
  ou `JP Solar Solutions | Proposta prévia – <local>`.
- Estrutura: saudação → agradecimento («Obrigado pelo seu pedido de orçamento através do nosso site e pela
  fatura que nos enviou.») → «Com base em <fatura de <período> / no que nos indicou (consumo, kVA, cobertura)>,
  preparámos a seguinte proposta:» → lista (n.º painéis Haitai 585 W TOPCon bifaciais (kWp); inversor híbrido
  Deye <modelo> (kW, mono/tri, backup); bateria Blue Carbon <kWh>; estrutura, cablagem, proteções, instalação,
  certificação e registo da UPAC) → produção estimada, poupança/ano, retorno em anos → **Investimento** →
  opções (sem bateria, bateria extra 2 298,40 € c/IVA, inversor maior) → nota de proposta prévia → próximo
  passo (visita/videochamada: «Indique-nos, por favor, dois dias e horas…», morada, telefone) →
  «Segue em anexo a nossa proposta.» → assinatura.
- Anexos: 1 PDF por cenário. Nome: `Proposta UPAC - <Nome> - <AAAA-MM-DD>.pdf`; variantes
  `Proposta UPAC - <Nome> - <8 paineis | Trifásico | Cenario 1 sem bateria> - <data>.pdf`,
  `Proposta UPAC A|B - <Empresa> <local> - <data>.pdf`. Fichas técnicas (painel, inversor, bateria,
  estrutura) quando o cliente as pede ou o texto as promete.
- Cc: nenhum. Se a geral@ (João) já enviou valor ao mesmo cliente, ler antes e dizer qual vale.
- Condições quando pedidas: 60% na adjudicação, 40% após instalação e comissionamento; validade 30 dias;
  obra 2 dias; garantias: painéis 12 anos produto / 30 rendimento, inversor 10 anos.

### 2. Proposta a empresa / empreiteiro / concurso (subempreitada, MQT)
- Assunto: mantém o do empreiteiro (`RE: Pedido de cotação`, `RE: Pedido e cotação "Empreitada de …"`).
- Abertura: `Boa tarde, Sr. <Nome>,` ou `Exmos. Srs.,` / `Exmo. Senhor Eng.º <Nome>,`.
  «Segue em anexo a nossa proposta para <capítulo/obra>, com o mapa de quantidades preenchido.»
- Valor: **`<valor> € s/IVA (IVA em regime de autoliquidação; com IVA a 23 % seriam <valor> €)`**, por capítulo
  e total. Para empreiteiro em obra pública/construção é sempre autoliquidação (já saiu uma com «+ IVA (… com
  IVA)» — inconsistente).
- Secções em negrito: «Nota importante – valores sujeitos a confirmação por visita técnica» (o que falta
  confirmar), «Âmbito» (incluído / não cotado / excluído: construção civil, andaimes, meios de elevação, taxas),
  «Equivalências e observações ao projeto» (Haitai 585 W em vez de <ref.>, «sujeita a aprovação do projetista»;
  discrepâncias entre caderno de encargos, MQT e unifilar), «Condições» (60/40 ou 30% + autos; validade 30 dias;
  garantia mão de obra), «Credenciais» (Entidade Instaladora DGEG n.º 3369; Alvará IMPIC 112765, Classe 3;
  Técnico Responsável DGEG n.º 89244). Fecho: «Caso a obra não nos seja adjudicada, agradecemos qualquer
  indicação sobre o posicionamento do nosso preço.»
- Anexos: PDF `Proposta Fornecimento e Montagem FV - <Empresa> - <data>.pdf`, `Cotacao UPAC - <Empresa> - <obra>
  - <data>.pdf`, `Proposta Postos VE - <Empresa> - <data>.pdf` + MQT preenchido (Excel) quando houve MQT.
- Cc: o que o cliente pediu (ex.: departamento financeiro). Respeitar o prazo de entrega indicado.

### 3. Primeira resposta a lead (pedido de dados)
- Assunto: `JP Solar Solutions | O seu pedido de orçamento solar` ou `RE: <assunto do pedido>`.
- Corpo: agradecer o pedido «através do nosso site»; «Para prepararmos uma proposta ajustada…, precisamos de:»
  lista — fatura recente (12 meses ou mês de inverno, PDF ou foto); morada/localidade (ou Google Maps);
  mono ou trifásico; tipo de edifício e de telhado (telha, chapa, terraço, solo); bateria? carro elétrico?;
  fotos do telhado e do quadro; telefone. Conversão de microprodução: marca/modelo do inversor e etiquetas dos
  painéis. Fecho: «Com estes dados enviamos-lhe uma proposta prévia… O orçamento final fica fechado depois de
  uma visita técnica, que é gratuita.» «Ficamos a aguardar o seu contacto.»
- Sem anexos. Também é aceite responder já com proposta prévia por escalão de fatura (assumindo consumo e
  dizendo o pressuposto: «assumindo um consumo de cerca de <n> kWh por mês»; «Assumimos uma instalação monofásica»).

### 4. Seguimento / marcação de visita técnica ou videochamada
- Assunto: `RE:` da conversa, ou novo `Visita técnica — <descrição> em <local>`.
- Propor duas opções concretas com dia da semana + data + hora (`Terça-feira, 24/11, às 10h00`), pedir
  telemóvel. Confirmação: «Fica confirmada a visita técnica na <dia>, <data>, de manhã, entre as 9h e as 13h,
  em <local>.» Videochamada: «gratuita, de 20 a 30 minutos (WhatsApp, Microsoft Teams ou Google Meet)»;
  listar o que mostrar (telhado, quadro, contador mono/tri, local do inversor e bateria).
- Coerência: se a primeira mensagem disse «visita gratuita», não dizer depois que tem custo sem explicar.
  Datas propostas devem bater com a disponibilidade que o cliente deu e com a agenda da Tindra.
- Formato de data: «quinta-feira, 12 de novembro, às 14h00» (minúscula, hífen, sem espaços antes da vírgula).

### 5. SOLENERGE → DREn (@azores.gov.pt)
- Responder SEMPRE em resposta ao email da DREn (a DREn exige «em resposta ao presente e-mail»), mantendo o
  assunto: `RE: SOLENERGE #<n.º> - Registo da Unidade de Produção para Autoconsumo`,
  `RE: SOLENERGE/<n.º>/<n.º> - Pedido de esclarecimento`, `RE: Solenerge <n.º>/<n.º>`.
- Registo UPAC: To `serup.energia@azores.gov.pt`, Cc o técnico da DREn que pediu + o beneficiário.
  «Exmos. Senhores, No seguimento do pedido de <data> relativo à candidatura SOLENERGE #<n.º> (<beneficiário>,
  NIF <…>), informamos que o registo da Unidade de Produção para Autoconsumo foi submetido no Portal da Energia,
  tendo-lhe sido atribuído o **ID <n.º>**. O registo foi instruído com o esquema unifilar, o termo de
  responsabilidade do técnico responsável pela execução (inscrito na DREn com o n.º 605/T), a declaração de
  limitação da potência de injeção e a fatura de eletricidade.» Sem anexos.
- Esclarecimentos: To o técnico que pediu (Cc beneficiário quando útil). «No seguimento do pedido de <data>
  [reiterado a <data>] relativo à candidatura SOLENERGE/<n.º> (<beneficiário>, NIF <…>), enviamos em anexo:»
  lista numerada a responder ponto a ponto ao pedido (certidão AT e declaração SS «emitidas a <data>»; fatura EDA;
  fotografias; lista de painéis; consignação; TR). Cada ponto pedido tem de ter resposta ou anexo.
- Anexos: PDF, nunca links (a DREn não abre links). Fotos agrupadas num PDF
  (`SOLENERGE_<n.º>_Fotografias_paineis_instalados.pdf`) em que se contem todos os painéis; `<n.º>_TR_assinado.pdf`;
  `Lista_Paineis_<n.º>.pdf`; `Contrato_Consignacao_<n.º>_assinado_gerente.pdf`. Renomear certidões genéricas
  (`consultaCertidao.action.pdf`, UUID, `IMG_…`) para `<n.º>_Certidao_AT_<data>.pdf` / `<n.º>_Declaracao_SS_<data>.pdf`.
- TR e documentos com data anterior a 31/08/2026 e assinatura manuscrita quando a DREn o exige.

### 6. SOLENERGE → cliente (pedido de documentos, fases, Fase 3)
- Assunto: `SOLENERGE <n.º> — <o que é preciso>` (travessão), ex.: `SOLENERGE <n.º> — recibo para colocar na
  plataforma`, `SOLENERGE <n.º> — falta só a fatura da EDA mais recente`, `URGENTE – Dados em falta para o
  registo da UPAC (SOLENERGE <n.º>)`.
- Saudar a pessoa dona do endereço (se é um intermediário, `Sr. <intermediário>` e citar `(D. <beneficiária>)`).
- Explicar em linguagem simples: «A SOLENERGE (DREn) pediu <x>, com prazo até <data>.» «Não se preocupe, é um passo
  normal do processo e nós tratamos dele.» Dividir «preparamos nós» / «precisamos que nos envie».
  Fase 3: «Boas notícias: a SOLENERGE já pagou o incentivo… prazo de 30 dias a contar do pagamento (até cerca de
  <data>)», anexar o recibo `RC_<ano>_<n.º>.pdf` e passos numerados (solenerge.azores.gov.pt → «Os meus processos»
  → «Abrir formulário»). Assinaturas: à mão igual ao CC ou digital CC/CMD; «não use assinaturas coladas como imagem».
- Fecho: «Basta responder a este email com <documentos>. Nós enviamos tudo à SOLENERGE.»
- Agradecer receção de documentos e dizer o que segue («Vamos juntá-las ao seu processo SOLENERGE/<n.º> e enviá-las à DREn.»).

### 7. Fornecedores (pedidos de cotação)
- Assunto: `Pedido de cotação – <produto> para <modelo/aplicação>`.
- Abertura: «Boa tarde, Somos a JP Solar Solutions, entidade instaladora (DGEG n.º 3369) com sede em Esmolfe,
  Penalva do Castelo.» Identificar equipamento (modelo, S/N quando relevante), material pretendido (lista com
  quantidades/referências) e «Agradecíamos que nos indicassem:» lista numerada (compatibilidade, preço unitário
  s/IVA com desconto de instalador, stock e prazo, portes, abertura de conta). Fecho: «Ficamos a aguardar o vosso contacto.»
- Estrangeiro: na língua do fornecedor; nome da empresa correto «JP Solar Solutions Lda» (já saiu «PSolar Solutions»).
- Cada fornecedor recebe email limpo e próprio: nunca reencaminhar (FW) a conversa de outro fornecedor.

### 8. Internos ao João / Pedro (não vão para clientes)
- Assunto com urgência e ação: `URGENTE SOLENERGE <n.º> (<cliente>) — assinar consignação como gerente`,
  `Encomenda – <material> para <fim>`, `URGENTE – Compra de <material>`.
- To joao.lopes@ (ou geral@ para João/Pedro), Cc geral@ quando envolve compras/pagamentos. Tom direto, «tu»,
  link SharePoint para o ficheiro a assinar, prazo da DREn, o que cada um tem de fazer.
- O revisor deve garantir que nada deste tom/conteúdo (links SharePoint, «assina tu», margens, decisões internas)
  aparece num email a cliente, e que o corpo cumpre tudo o que o assunto promete.

### Outros tipos vistos
- Envio de fatura: `Fatura FT <ano>/<n.º> - JP Solar Solutions`; valor total, já pago, em falta.
- Certificação ao cliente: «a instalação … já se encontra certificada. Segue em anexo o certificado (Declaração
  de Conformidade de Execução).» Suporte Deye: em inglês, com SN, plant, firmware, capturas.
- Campanha a eletricistas: enviar com o Mickael em Para e os destinatários em Bcc (verificar que não vão em Para).

## (c) Erros já cometidos → o que verificar

| Erro real (data) | Verificação |
|---|---|
| «Segue em anexo» sem anexo: proposta Quinta (06/11), 3 cenários (02/11), MQT de concurso (23/09), fichas técnicas (16/11), fichas + planta (09/11) | Cada «segue em anexo / em anexo / juntamos» tem ficheiro anexado; contar: n.º de PDFs = n.º de cenários/documentos citados |
| Dois emails ao mesmo cliente com 4 s de diferença e valores diferentes (7 676,18 vs 7 678,15) | Não há outro rascunho/envio recente para o mesmo endereço; um só email por proposta |
| Cliente recebeu proposta da geral@/chat e outra do Mickael (Edgar, Vitor, Salazar) | Ler Tindra e enviados da geral@ antes; se já houve valor, dizer qual vale e porquê |
| Placeholder enviado: «Propomos [CONFIRMAR: dia e hora — ex.: …]» (20/10) | Procurar `[`, `CONFIRMAR`, `XX`, `<`, `ex.:` |
| Sem assinatura ou só «Com os melhores cumprimentos,» (Dierre, Vitor Faim, Taberna, DFG, concurso) ; fecho duplicado | Bloco de assinatura completo, uma vez |
| Saudação sem nome («Boa tarde,», «Bom dia,»), «Caro Davide» com cliente David, «Everdina» sem D., «Lidia» sem acento | Nome = assinatura do cliente/Tindra; Sr./D.; acentos |
| «Bom dia» enviado às 17h04 | Saudação vs hora de envio |
| Email ao intermediário a saudar a beneficiária («D. Ana» no email do Roger) | Saudar quem lê o endereço |
| Fotos duplicadas (foto2/4/5 anexadas 2×) ; fotos por link que a DREn não abriu ; fotos sem todos os painéis («engano meu») | Sem anexos repetidos; fotos em PDF anexo; n.º de painéis nas fotos = fatura = lista de SN |
| Lista de SN com 16 painéis para fatura de 17 ; TR com data/minuta errada | Contagens e datas coerentes entre fatura, lista, fotos, TR |
| Certidões enviadas como email novo a solenerge@ em vez de resposta ao pedido | DREn: sempre RE: ao email do técnico, assunto intacto |
| Concurso com «+ IVA (… com IVA a 23 %)» quando outros do mesmo empreiteiro foram autoliquidação; condições 30% vs 60/40 | Empreiteiro → autoliquidação; condições iguais às da proposta PDF |
| FW de cotação a fornecedor com a conversa de outro fornecedor e «PSolar Solutions»; corpo sem parágrafos | Email limpo por fornecedor, nome da empresa correto, formatação |
| Resposta irónica/insultuosa a lead (23/09) | Tom sempre cortês; se o cliente for rude, não responder ou resposta neutra |
| Assunto com 2 pontos e corpo só com o 1.º (interno 16/11) | Corpo cobre tudo o que o assunto e o pedido original pedem |
| Ortografia pré-AO («actualmente», «eléctrico», «protecções») ; «dia 12 , Quinta feira ,» | AO90, pontuação, dias da semana em minúscula com hífen |
| Ficha técnica anexada de modelo diferente do indicado no texto (SUN-14K vs ficha 15-20K) | Fichas = modelos da proposta |
| PDF com nome genérico («Cliente Guarda», «comprovativo (8).pdf», UUID) ou data antiga no nome | Nome do PDF segue a convenção e tem o cliente/n.º processo |
| Email do telemóvel sem assunto e sem texto («Enviado de Outlook para Android») | Assunto preenchido e frase a explicar o anexo |
| Pedir ao cliente utilizador e palavra-passe por email | Preferir telefone; nunca reenviar credenciais por email |

## (d) Lista de verificação final (revisor)

1. Destinatário certo (Para/Cc/Bcc); DREn: resposta na conversa, serup.energia@ no registo, cliente em Cc.
2. Assunto no formato do tipo; RE: mantido; n.º de processo/orçamento correto.
3. Saudação: nome exato com acentos, Sr./D./Exmo., Bom dia/Boa tarde conforme hora de envio.
4. Sem marcadores (`[CONFIRMAR]`, `XX`, `<…>`) nem texto interno (SharePoint, «assina tu», margens).
5. Cada anexo citado existe; nomes segundo a convenção; sem duplicados; PDF em vez de link; fichas = modelos.
6. Valores: email = PDF = Tindra; com/sem IVA corretos (×1,23); autoliquidação para empreiteiros; formato `1 234,56 €`.
7. Contagens coerentes (painéis, kWp, SN, fotos) e datas certas (prazos DREn, datas de visita com dia da semana).
8. Não existe outra proposta/email recente ao mesmo cliente (Mickael, geral@, plataformas) com valores diferentes.
9. Todos os pontos pedidos pelo cliente/DREn respondidos; próximo passo claro (o que o cliente faz, até quando).
10. Português de Portugal AO90, tom cordial, assinatura completa uma só vez.
