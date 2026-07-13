---
tema: Comunicação (Hermes), Suporte e Operação Cadê
data: 2026-07-05
status: em construção
---

# Comunicação, Suporte e Operação

> Transversais que atravessam todas as jornadas. Hoje: o agente **Hermes** só faz suporte; follow-up é checklist manual (sem WhatsApp automático); operação interna (quem atende/aprova) é indefinida.

> [!abstract] Base de pesquisa
> Sugestões deste doc vêm de [[03 - IA Verificacao e Comunicacao BR-US]] §2 (números, custos e fontes lá). Alerta-chave: a **Meta mudou o preço do WhatsApp API em jul/2025** (por mensagem de template, não mais por conversa 24h).

## 1. Comunicação / Hermes 🆕
> [!todo] ✍️ PRECISA ESCREVER
> - Que **mensagens** o sistema/Hermes envia, **quando** e por **qual canal** (in-app, e-mail, WhatsApp)?
> - A comunicação muda por tipo de usuário (comprador × locatário × proprietário × corretor)? (O João frisou: "o questionamento do usuário de aluguel é diferente do de compra.")
> - Os follow-ups **7/30/45 dias** viram **envio automático de WhatsApp** (ReMKT) ou seguem manuais?
> - Regras de LGPD: que contexto do negócio a IA pode ler/usar?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** o WhatsApp é **o** canal no Brasil, e a maior alavanca de conversão é **velocidade** — responder em **≤5 min = ~21× mais conversão**; **78% dos compradores fecham com o primeiro que responde**. O follow-up importa muito: **80% das vendas exigem 5+ toques**, e a maioria dos vendedores nunca faz.
> **Recomendação para o Cadê — desenhar o Hermes como 3 tipos de mensagem:**
> - **Transacional/utility** (confirmação de visita, lembrete D-1, mudança de status da esteira): via **template de utility do WhatsApp API — grátis dentro da janela de 24h** (novo modelo Meta jul/2025). Barato, alto valor. **[MVP]**.
> - **Acknowledgment instantâneo** (responder o lead em <1 min, mesmo fora do horário — 62% chegam fora do expediente): bot que confirma recebimento e faz a 1ª qualificação. **[MVP]** — é o maior ROI.
> - **Nutrição/ReMKT** (cadência **7/30/45 dias**, reengajamento por gatilho): sugiro **automatizar via WhatsApp/e-mail** (não manter manual — o manual não acontece). Marketing template é pago (~US$0,06/msg BR); nutrição por gatilho (novo imóvel do perfil, queda de preço) converte melhor que "só passando pra saber". **[Fase 2]** para a cadência automática completa.
> - **Comunicação muda por ator (o ponto do João):** sim — o script de qualificação do **locatário** gira em torno de renda/garantia/prazo; o do **comprador** em torno de ticket/financiamento/perfil; o do **proprietário** em torno de captação/documentos; o do **corretor** em torno de leads/agenda. Um **template + fluxo de IA por ator**, não um genérico.
> - **Lead que vem de anúncio Click-to-WhatsApp = 72h grátis** (Free Entry Point) — ouro para a Cadê que roda tráfego pago; casar comunicação com a mídia paga.
> **LGPD [obrigatório]:** consentimento de WhatsApp é **separado** do de e-mail; opt-in registrado (timestamp/IP/finalidade); opt-out por palavra-chave em ≤24h. **WhatsApp pessoal do corretor é risco crítico** — usar **API oficial + inbox corporativa** (o Cadê já bloqueia troca de contato ✅, o que ajuda). A IA lê o contexto do negócio **dentro da finalidade consentida**; conteúdo de usuário = dado, nunca comando (prompt injection).
> **Decisão dos sócios / trade-offs:** qual BSP (360dialog markup-zero vs Zenvia/Take Blip com faturamento/suporte BR) e quanto automatizar de nutrição no go-live. Recomendo utility + acknowledgment no MVP; marketing/nutrição automatizada na Fase 2.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §2.1-2.2, §2.5.

## 2. Suporte e handoff humano ✍️
> [!todo] ✍️ PRECISA ESCREVER
> O suporte por IA existe (FAQ + busca de imóvel). Definir: quando escala para humano, **onde cai** esse atendimento (inbox / horário / SLA / quem atende), e o escopo do suporte **pós-conclusão** por tipo de negócio.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** o padrão é **IA na frente, humano no gargalo**. A IA (Hermes) resolve FAQ + busca + qualificação + agendamento; escala para humano por **gatilhos claros de warm handoff**: (1) usuário pede humano; (2) precisa comparar/negociar algo fora do script; (3) **negócio de ticket alto**; (4) pergunta que a base não responde após 2 tentativas; (5) **lead quente pronto pra visita/proposta**. No handoff, o humano recebe **o transcript + a qualificação** (não recomeça do zero).
> **Recomendação para o Cadê:**
> - **[MVP]:** Hermes faz o primeiro atendimento; handoff por regra simples (pediu humano / qualificou / fora do escopo) → cai numa **inbox corporativa** (do time interno Cadê, ver §3) com o transcript anexado. Definir **SLA** (ex.: resposta humana no próximo horário útil) e **horário** de plantão humano; fora dele, a IA cobre e promete retorno.
> - **Pós-conclusão por tipo de negócio:** **locação** tem suporte contínuo (manutenção, cobrança, renovação — se administrada); **venda** é pontual (pós-fechamento resolve pendência de documento/cartório e encerra). Modelar os dois escopos diferentes.
> - **[Fase 2]:** roteamento por especialidade, scoring de urgência, base de conhecimento que melhora sozinha.
> **Decisão dos sócios / trade-offs:** onde cai o humano (corretor parceiro? time interno Cadê? — ver §3) e o SLA prometido. Quanto mais a IA resolve, menor o custo de operação — mas handoff ruim frustra. Recomendo IA ampla + handoff rápido e com contexto.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §2.4-2.5.

## 3. Operação Cadê (admin/time interno) 🆕
> [!todo] ✍️ PRECISA ESCREVER
> A visão diz "e-mails/ligações apenas com o time interno da Cadê" e há painel admin (usuários, corretores, prestadores, suporte). Definir a **jornada do operador Cadê**: quem atende leads, quem opera o cartório, quem aprova prestadores/corretores, quem faz as ligações — e como isso aparece no sistema.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** as plataformas transacionais têm um **time de operação interno** que faz o que a IA e o corretor parceiro não fazem: aprovar cadastros/prestadores, tratar exceções, operar a esteira crítica (contrato, cartório), atender o handoff humano. É a "cola" invisível — e precisa ter **tela própria** (painel admin) e **papéis** definidos.
> **Recomendação para o Cadê — definir os papéis de operador (reusam o modelo de `papéis` do código):**
> - **Atendimento/SDR interno:** recebe o handoff da IA, faz ligações (o "e-mails/ligações só com time interno" do UX), converte lead. Distribuição por **roleta** (round-robin/plantão).
> - **Aprovador de prestadores/corretores:** valida CRECI do corretor (ver [[04 - Corretor (Parceiro)]] §1) e aprova despachante/advogado do marketplace de fechamento (ver [[05 - Fechamento (transversal)]] §3). Critério definido pelos sócios.
> - **Operador de esteira/cartório:** acompanha documentos, aciona o despachante, confirma o registro na matrícula ("concluído"). Ver [[05 - Fechamento (transversal)]].
> - **Suporte N2:** o humano que recebe o escalonamento do Hermes (§2).
> **Recomendação de fase:** **[MVP]** o painel admin já existe no código — priorizar as telas de **aprovação (corretor/prestador)** e **inbox de handoff**; o resto da operação pode rodar com processo manual apoiado no painel. **[Fase 2]** distribuição automática, dashboards de conversão por operador, SLA monitorado.
> **Decisão dos sócios / trade-offs:** **quem é esse time no começo** (os próprios sócios? contratados?) e quanto da operação é humano vs automatizado no go-live. Capacidade importa — definir o mínimo de operação que sustenta o volume esperado do lançamento. É a decisão que conecta o produto à realidade de quem vai tocá-lo no dia 01/08.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §2.3-2.4 · [[10 - Dossie do Sistema (as-built)]] (painel admin).
