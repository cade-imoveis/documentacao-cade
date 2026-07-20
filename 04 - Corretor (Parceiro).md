---
ator: Corretor / Parceiro
data: 2026-07-05
status: em construção
---

# Jornada do Corretor / Parceiro

> 🆕 O papel `corretor` existe no código e é **lido em todo lugar** (documentos, comissão, follow-ups), mas **não há nenhuma tela/ação que coloque um corretor num negócio** — só insert manual de admin. Jornada a definir do zero.

> [!success] ✅ DECISÃO A4 + P4 — Jornada do Corretor (17/07/2026, Fernando)
> Modelo: **corretor parceiro PJ**, sem vínculo empregatício. Um marketplace de corretores com **reputação gamificada**, orquestrado pela IA **Amanda**. Preço em [[06 - Planos, Serviços e Precificação]].
>
> **Requisito de entrada:** CRECI **ativo** obrigatório (Lei 6.530/78). Validação **sem custo**: no MVP, checagem **manual** pela **consulta pública do CRECI-UF** no passo de validação do jurídico. API automatizada paga (ex.: IMOBISEC) só na Fase 2, quando o volume justificar.
>
> **Onboarding:** cadastro com a mesma experiência da captação de imóvel, preenche dados, validação (jurídico + CRECI), fica ativo.
>
> **Score adaptativo (define o volume de leads):** corretor novo pesa mais em **contribuição** (captação de imóveis, trilha) + piso de justiça; com histórico, o peso migra para **desempenho** (fechamentos, nota do cliente, velocidade). Pilares: captação de imóveis, captação de corretores, trilha + provas, avaliação do cliente, nº de atendimentos/agendamentos/fechamentos.
>
> **Distribuição de leads:** automática, **weighted-random** (sorteio ponderado pelo score) com **piso para novatos**; filtros duros por cidade/região + disponibilidade. O comprador pode **escolher o corretor pelo nome** ou **pedir atendimento** (aí entra o sorteio ponderado). A Amanda roteia.
>
> **SLA (o lead já vem atendido pela Amanda):** 1º contato do corretor em **até 5 min**; evolução na esteira em **até 5h** por etapa; sem evoluir, o lead **volta à base e re-atribui**. Estados: Novo → Contato → Agendado → Proposta → Fechado/Perdido.
>
> **Segmentação:** por cidade e região/bairro (especialista) ou generalista.
>
> **Captação e ganhos (regra anti-pirâmide):**
> - Captação de **IMÓVEL**: score (mais leads) + **comissão de captador** quando o imóvel vende.
> - Captação de **CORRETOR**: **só score** (mais leads), nunca dinheiro sobre a produção do indicado. Sem níveis, sem renda recorrente.
>
> **Vendas em parceria** (captador × vendedor): podem ocorrer, com percentuais **a definir** no contrato de parceria PJ.
>
> **Exclusividade (correção):** é do **imóvel com o Cadê** (comercializado só pelo Cadê, 4%); internamente é trabalhado por **qualquer/todos** os corretores da base. Não-exclusivo = 5%.
>
> **Assinatura do corretor (4ª receita):** Anual **R$ 49,90/mês** (12 meses) · Livre **R$ 99,90/mês**. Abatimento (Opção A): cada negócio fechado gera crédito que abate a próxima mensalidade, podendo zerar.
>
> **Corte MVP:** cadastro + validação CRECI manual + atribuição por cidade/região + SLA + score básico (atendimentos/agendamentos/fechamentos) + escolha pelo nome ou pedir atendimento + assinatura. **Fase 1.5/2:** trilha + provas, captação de corretores no score, weighted-random sofisticado, especialista por bairro, API de CRECI.
>
> 🔴 **Especialista:** contrato de parceria PJ (incl. split captador×vendedor), regras COFECI de vitrine/publicidade do corretor, e desenho do bônus de indicação caso vire cash (manter pontual, capado, nível único).

## 1. Cadastro / onboarding do corretor 🆕
> [!todo] ✍️ PRECISA ESCREVER
> - Corretor se cadastra sozinho (com verificação de **CRECI**) ou é aprovado por admin?
> - Que dados/documentos entram? Vincula a uma imobiliária (CNPJ)?

> [!abstract] Base de pesquisa
> Sugestões deste doc vêm de [[01 - Locacao e Corretor BR-US]] §2 (números e fontes lá).

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR) [parte é lei]:** CRECI ativo é **obrigatório** (Lei 6.530/78 — intermediação é atividade privativa). O padrão de onboarding das plataformas **não é self-service puro — é aprovação com verificação documental**: formulário + docs → valida CRECI → convite de associação → contrato → ativo. O corretor pode ser **autônomo sem imobiliária** (Lei 13.097/2015 criou o "corretor associado", exatamente o enquadramento de "corretor parceiro"). Exige CRECI **"ativo e definitivo"** (não provisório).
> **Recomendação para o Cadê:** **cadastro self-service + verificação automática de CRECI + ativação por aprovação** (híbrido). A verificação é automatizável via **IMOBISEC** (API que consolida os CRECIs de todos os estados, feita para proptechs) ou consulta pública do CRECI regional. Dados mínimos: nome, CPF, nº e UF do CRECI, selfie+documento; vínculo com imobiliária (CNPJ) **opcional** (aceitar PF autônomo e PJ). **[MVP]** o cadastro + verificação; liberação por região vem depois.
> **Decisão dos sócios / trade-offs:** verificação automática (IMOBISEC tem custo por consulta) vs manual (admin confere — grátis mas não escala). Recomendo automática desde o início — é barato e evita corretor sem registro no sistema (risco jurídico).
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §2.1.

## 2. Entrada num negócio 🆕
> [!todo] ✍️ PRECISA ESCREVER — o buraco central
> Como um corretor entra num negócio específico? Ele **se candidata** a leads, é **convidado** pelo proprietário, ou o **admin atribui**? Um imóvel pode ter proprietário **e** corretor ao mesmo tempo? Há exclusividade?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** no BR o corretor **recebe lead por atribuição/pool, não por candidatura** (diferente do Zillow US, que é leilão de lead por CEP — não transferível). QuintoAndar entrega ao corretor de visita um **lead já qualificado, muitas vezes com visita já agendada**. Coexistem 4 modelos: atribuição/pool (dominante), corretor traz a própria carteira, atribuição por imóvel/convite ("Corretor com Chaves"), e candidatura (rara).
> - **Exclusividade NÃO é obrigatória** (art. 726 CC, opcional). O **default cultural é não-exclusivo**: o mesmo imóvel pode estar com **proprietário direto + vários corretores ao mesmo tempo**.
> **Recomendação para o Cadê — modelar como flags no `negócio` (a esteira as-built já suporta papéis):**
> - Suportar **imóvel com proprietário direto E corretor(es)** simultâneos — é a realidade do mercado, não um caso de borda. Tratar **exclusividade como um estado especial** do imóvel que muda quem tem direito à comissão.
> - Para o MVP, o mecanismo mais simples e alinhado ao BR é **atribuição** (admin/plataforma vincula o corretor ao negócio ou ao pool de leads de uma região) + **convite do proprietário** (quando ele escolhe "atendimento com corretor" no doc [[01 - Proprietário]] §5). Candidatura a leads (pull) = **[Fase 2]**, só se fizer sentido.
> **Decisão dos sócios / trade-offs:** este é o **buraco central** que o João apontou — nenhuma tela hoje coloca corretor num negócio. Definir o mecanismo de entrada destrava o desenvolvimento. Atribuição é o mais simples; distribuição por pool/rodízio com regras é mais justo mas mais complexo. Amarra-se ao doc [[06 - Planos, Serviços e Precificação]] §"Como o serviço muda a jornada".
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §2.2-2.3.

## 3. Carteira 🆕
> [!todo] ✍️ PRECISA ESCREVER
> Existe **carteira** (imóveis e leads do corretor), como o marketing promete, ou é só um selo de CRECI? Se existe: o corretor traz os próprios imóveis? recebe leads do pool? como são distribuídos?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** a carteira **existe de verdade** nas plataformas maduras — não é só selo. No app do corretor QuintoAndar: carteira de **clientes/leads por etapa** (funil, propostas, anotações) + acesso à **base ampla de imóveis** (não só os que ele captou) + **agenda de visitas** integrada (marcar/confirmar/reagendar com notificação automática). O corretor pode **trazer os próprios imóveis** (papel de captador/consultor) **e** receber leads do pool.
> **Recomendação para o Cadê:** carteira = **a visão do corretor sobre seus negócios** (os `negócios` em que ele tem o papel `corretor`) + os imóveis que ele captou + os leads atribuídos. Reusa o modelo `negócio`+`papéis` que já existe — é uma **tela de listagem filtrada por papel**, não uma estrutura nova. **[Fase 2]** (depende de o corretor entrar em negócios, §2). Para não fazer código genérico: começar com **carteira = lista dos negócios do corretor + agenda de visitas**; distribuição automática de leads do pool é o incremento seguinte.
> **Decisão dos sócios / trade-offs:** carteira rica (funil + CRM + nurture) é o que retém o bom corretor, mas é muito produto. Sugiro MVP mínimo (lista + agenda) e evoluir. O CRM completo (cadências, speed-to-lead) é o padrão US (Follow Up Boss/kvCORE) — bom norte de Fase 2+.
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §2.3, §2.5.

## 4. Comissão e repasse ✍️
> [!todo] ✍️ PRECISA ESCREVER (cálculo já existe, é informativo)
> A plataforma **calcula e repassa** a comissão, ou é só registro? Qual a **taxa** (hoje 6% venda / 1 aluguel são só defaults de tela)? Como divide captador × vendedor? Quem é o pagador por tipo de negócio?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** os defaults do código estão **certos como âncora** — **venda ~6%** (teto CRECI/mercado; QuintoAndar até 6%) e **locação = 1 aluguel** de corretagem + administração recorrente (QuintoAndar 9,3%/mês; mercado 8-12%). Quem paga: **o proprietário/vendedor** (o comprador não paga corretagem no BR). O split captador×vendedor tradicional é **50/50**, mas varia por imobiliária.
> **Recomendação para o Cadê — decidir "registro" vs "repasse":**
> - **[MVP] Comissão informativa (registro):** a plataforma **calcula e mostra** a comissão; o pagamento e o repasse ao corretor acontecem **off-app**. É o que o código já faz. Esforço zero, sem risco regulatório.
> - **[Fase 2+] Comissão intermediada (repasse):** a Cadê **recebe e repassa** a comissão via split num PSP — exige o módulo de pagamentos (ver [[06 - Planos, Serviços e Precificação]] §"O dinheiro passa pela plataforma?"). Só vale quando houver volume; e depende de a jornada do corretor existir (§§1-3 deste doc, ainda a escrever na Fase 2).
> **Decisão dos sócios / trade-offs:** a taxa exata é aposta de sócio (manter 6% ou entrar abaixo como diferencial). O split captador×vendedor e quem é o pagador por tipo de negócio dependem de o corretor ser cliente-pagante ou parceiro de aquisição — decisão que se amarra à jornada do corretor.
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1 (comissão BR), §3.1-3.4 (split/repasse).
