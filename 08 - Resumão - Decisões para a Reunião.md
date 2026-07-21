---
tema: Pauta de decisões para a reunião dos sócios
data: 2026-07-12
status: pronto para reunião
autor: Douglas (COO) — consolidação das sugestões a validar
---

# 🗣️ Resumão — Decisões para a reunião dos sócios

> [!info] O que é isto
> Consolidação de **todas as decisões abertas** espalhadas pelos fluxos (docs 01-07). Cada fluxo trouxe uma sugestão minha (baseada em pesquisa de mercado BR+US 2025-2026); aqui ficam **só as decisões que dependem de vocês** — o que eu recomendo e o trade-off. Objetivo: uma reunião, um documento, decisões batidas. Nada aqui está decidido.
> **Fonte das recomendações:** dossiê em `06 - Conhecimento/Mercado Imobiliario Tech BR-US/` (4 notas). Cada linha aponta o fluxo de origem.

> [!warning] Régua de prazo
> Meta do João: **01/08**. Etiquetei cada decisão como **🔴 destrava o João agora** · **🟡 regra de negócio a cravar** · **🟢 escopo (MVP vs Fase 2)**. Comecem pelas 🔴 — sem elas o desenvolvimento fica no ar.

---

## ⭐ Parte 1 — As decisões-âncora (🔴 resolver primeiro)

Estas seis destravam metade das outras. Se a reunião só resolver estas, já valeu.

### A1. Qual é o modelo de receita âncora? → [[06 - Planos, Serviços e Precificação]]
O maior bloqueador. Define o produto inteiro.
| Opção | Receita | A favor | Contra |
|---|---|---|---|
| **A) Transacional** (tipo QuintoAndar) | comissão de venda/locação | alinha ao sucesso; anunciar grátis atrai inventário | só fatura quando fecha; ciclo longo; exige entregar o fechamento |
| **B) Portal/assinatura** (tipo ZAP) | assinatura + destaque | recorrente previsível dia 1 | exige volume de anunciantes |
| **C) Híbrido serviços** | avulsos + destaque (comissão opcional) | margem alta, baixo esforço, **começa já** | receita fragmentada, menos lock-in |
> **Recomendação Douglas:** **(C) + anunciar grátis** no go-live (menor esforço/risco), com (A) amadurecendo em paralelo. (A) é o maior valor no longo prazo, mas depende da esteira de fechamento redonda.
>
> ✅ **DECIDIDO (16/07/2026, Fernando):** híbrido **SaaS + comissão** (cadastro grátis + assinaturas de ranqueamento/IA + comissão de 5% no full-service, 4% na exclusividade). A comissão fica habilitada via **CRECI-J da Versales**. Catálogo, preços, pagamento (A2) e itens de especialista consolidados em [[06 - Planos, Serviços e Precificação]] (seção "Decisões dos Sócios").

### A2. O dinheiro passa pela plataforma? → [[06 - Planos, Serviços e Precificação]] · [[05 - Fechamento (transversal)]] §4
Decisão que define esforço técnico enorme.
- **Nível 1 — cobrar serviços avulsos** (foto, jurídico, destaque): checkout simples, 1 PSP, sem split. **Baixo esforço.**
- **Nível 2 — intermediar o negócio** (sinal, aluguel recorrente, split de corretagem): mini-produto de pagamentos (KYC + split + ledger + conciliação + custódia) + **fronteira regulatória do BC** (manter saldo de terceiros em nome próprio exige autorização prévia). **Semanas-meses.**
> **Recomendação Douglas:** **Nível 1 no MVP, Nível 2 só quando o volume justificar.**

### A3. Catálogo do MVP — o que entra até 01/08? → [[06 - Planos, Serviços e Precificação]] · [[01 - Proprietário]] §5
Os "6 serviços" da 3ª tela do proprietário reorganizados em 3 famílias (Exposição · Atendimento & venda · Avulsos).
> **Recomendação Douglas:** MVP mínimo vendável = **postar (grátis) + jurídico (pacote) + destaque (avulso)**. Corretor/visita/IA-avançada = Fase 2. Evita o João codar os 6 genéricos agora.
>
> ✅ **DECIDIDO (17/07/2026, Fernando):** MVP entrega captação grátis + vitrine + ranqueamento + IA de atendimento (resultado-IA) + selo KYC + **modelo de transação completo e pronto** (Versales opera no interim por economia de recurso; migração ao Cadê condicionada a CRECI-J + alteração de CNPJ). Meta 01/08 mantida. Detalhe em [[06 - Planos, Serviços e Precificação]] (seção Decisões dos Sócios).

### A4. Como um corretor entra num negócio? → [[04 - Corretor (Parceiro)]] §2
O "buraco central" — hoje nenhuma tela coloca corretor num negócio.
- Opções: **atribuição** (admin/plataforma vincula) · **pool/rodízio** · **convite do proprietário** · candidatura (rara no BR).
> **Recomendação Douglas:** **atribuição + convite do proprietário** no MVP (mais simples e alinhado ao BR). Modelar o dado para aceitar **imóvel com dono direto + vários corretores** (não-exclusivo é o default legal, art. 726 CC).
>
> ✅ **DECIDIDO (17/07/2026, Fernando):** corretor parceiro PJ com **score gamificado** que define o volume de leads; **distribuição automática** (weighted-random por score, com piso), **SLA 5min/5h** e reciclagem de lead; entrada exige **CRECI ativo** (validação manual sem custo no MVP); **assinatura** R$ 49,90 anual / R$ 99,90 livre com abatimento por fechamento; captar imóvel gera comissão de captador, captar corretor gera **só score** (anti-pirâmide). Exclusividade = imóvel exclusivo do Cadê, trabalhado por toda a base. Detalhe em [[04 - Corretor (Parceiro)]].

### A5. A Cadê administra o aluguel ou entrega o contrato e sai? → [[03 - Locatário (Aluguel)]] §4
Decisão de escopo mais pesada da locação.
- **Sem administração:** fecha o contrato e sai. Zero módulo de cobrança recorrente.
- **Administrado:** cobra, repassa líquido, e no premium **garante o aluguel** (paga o proprietário mesmo com inadimplência) → risco de crédito no balanço, quase virar financeira.
> **Recomendação Douglas:** **"sem administração" no go-live**; administração como aposta de Fase 2 quando houver volume e caixa.
>
> ✅ **DECIDIDO (17/07/2026, Fernando):** locação **no MVP sem administração** (corretagem = 1 aluguel; garantias = análise de crédito + seguro-fiança). **Administração na Fase 1.5** (necessária, não bloqueia o 01/08): taxa **8,5%**/mês + **seguro locatício obrigatório** (garantidora = seguradora, sem risco de crédito ao Cadê) + corretagem no fechamento; via PSP + parceria SUSEP. Detalhe em [[03 - Locatário (Aluguel)]].

### A6. O que o MVP entrega de cada jornada — experiência-IA ou resultado-IA? → [[01 - Proprietário]] §1 · [[02 - Comprador]] §1/§3
O UX CADE.txt sonha com chat-IA, mapa interativo, ranqueamento comportamental — tudo caro.
> **Recomendação Douglas:** entregar o **valor** sem a **interface** cara no MVP: descrição+foto por IA e ranking semântico (pgvector) **sim**; chat conversacional, mapa interativo e reranking comportamental **na Fase 2**. O resultado relevante vem antes da interface.
>
> ✅ **DECIDIDO (17/07/2026, Fernando):** MVP = **resultado-IA** (a Amanda **faz**, não **conversa**): legenda/descrição + realce de foto no cadastro, ranking semântico (pgvector) na busca, e a **Amanda como SDR** (qualifica, agenda, nutre, roteia ao corretor, cobra o SLA). **Experiência-IA** (chat como interface, OCR de documentos, mapa interativo, reranking comportamental) = Fase 2. Isso **antecipa a Amanda** (era Fase 2 no plano fundador) para o MVP. Cadastro por chat = Fase 2, MAS o cadastro é a **ferramenta nº 1 de captação**, então 🔴 validar com o dev quanto do cadastro assistido cabe no MVP (formulário + IA → wizard guiado → chat), priorizando por ser captação.

---

## Parte 2 — Decisões por fluxo

### 💰 Planos, Serviços e Precificação → [[06 - Planos, Serviços e Precificação]]

> 💳 **Crédito via Teddy (nova linha de receita, 17/07/2026):** Cadê e Versales são parceiros da **Teddy Open Finance / The House** (marketplace multibanco). Originação dentro da jornada com **participação nas operações**, sem risco de crédito. Comprador: financiamento + consórcio; **proprietário: home equity** (owner-first). Fecha o lado do crédito da "última milha". Detalhe em [[06 - Planos, Serviços e Precificação]].
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| P1 | **Preço de cada serviço** (o número) | 🟡 | Aposta de sócio. Dei faixas de mercado na tabela-catálogo do doc 06 como ponto de partida. |
| P2 | **Comissão de venda**: manter ~6% ou entrar abaixo como diferencial? | 🟡 | Ancorar em ≤6% (teto CRECI/mercado). Entrar abaixo é posicionamento (EmCasa faz, sem publicar número). |
| P3 | **Quem paga cada coisa** | 🟡 | Proprietário/vendedor é o pagador principal. **Não** cobrar o comprador (nenhum concorrente BR cobra). Cobrar inquilino = risco jurídico (ver Parte 3). |
| P4 | **Mapa serviço → etapas** (como o serviço muda a jornada) | ✅ | **DECIDIDO (17/07/2026, Fernando):** flags no `negócio` (liga/desliga etapas); **Divulgação** (self-service + Amanda) vs **Full-service** (corretor + fechamento + despachante); **upsell da Amanda** de divulgação → full-service; **placa/adesivo** (grátis full-service, R$ 29/39/49 divulgação, com contato do Cadê); **exclusividade** 4% (1% de desconto + evidência dupla comprador/corretor). Ver [[06 - Planos, Serviços e Precificação]]. |

### 🏠 Proprietário → [[01 - Proprietário]]
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| PR1 | **Selo de verificação: obrigatório ou opcional?** | 🟡 | Opcional mas fortemente incentivado (verificado ganha ranking). Obrigatório reduz inventário. |
| PR2 | **Selo: grátis ou pago?** | 🟡 | Identidade grátis (higiene da base); verificação de propriedade como serviço premium. |
| PR3 | **Selo: identidade [MVP] / propriedade via matrícula [Fase 2]** | 🟢 | KYC é barato e pronto; verificação de propriedade depende de OCR de matrícula com humano no loop. |

### 🔑 Comprador → [[02 - Comprador]]

> ✅ **DECIDIDO (17/07/2026, Fernando):** C1 filtro + ranking semântico (MVP), chat Fase 2 · C2 amei/salvar + lista (MVP), mapa Fase 2 · C3 leve no interesse, validação de documento na visita · C4 vitrine mostra **localização aproximada** (bairro + ponto de referência), **endereço exato só após cadastro + validação** · C5 proposta **não** trava (proposta ≠ contrato); só **contrato assinado** bloqueia (proprietário pode barrar outras por conta própria) · C6 manter bloqueio de contato, sem investir em máscara. Detalhe em [[02 - Comprador]].
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| C1 | **Busca conversacional no MVP** ou filtro + ranking semântico? | 🟢 | Filtro + ranking semântico (pgvector) no MVP; chat na Fase 2. |
| C2 | **Mapa interativo**: MVP ou Fase 2? | 🟢 | Fase 2 (é caro). "Amei/salvar" + lista de seleção + destaque pago = MVP. |
| C3 | **Qualificação obrigatória para avançar?** | 🟡 | Leve no interesse; **rígida (validação de documento) antes da visita**. |
| C4 | **Quando liberar o endereço exato?** | 🟡 | Após qualificação/validação de documento, não só "ter interesse". |
| C5 | **Múltiplas propostas na compra**: aceita várias ou uma trava? | 🟡 | Na compra, proposta tende a ser exclusiva/vinculante (com sinal) — decidir. (Locação aceita várias — ver doc 03.) |
| C6 | **Anti-desintermediação**: quanto investir? | 🟢 | Manter o bloqueio que existe (higiene); **não** investir em mascaramento perfeito — retém é o valor on-platform. |

### 🏘️ Locatário (Aluguel) → [[03 - Locatário (Aluguel)]]
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| L1 | **Quais garantias aceitar no MVP?** | 🟡 | Só **análise de crédito + seguro-fiança** (padrão proptech, menos regra). Uma garantia por contrato (lei). |
| L2 | **Análise de crédito: própria ou terceirizada?** | 🟡 | Terceirizar a uma seguradora de fiança no início (própria = assumir risco, vira produto). |
| L3 | **Quão dura a pré-qualificação na busca** | 🟢 | Leve no topo, rígida só na proposta. |

### 🤝 Corretor (Parceiro) → [[04 - Corretor (Parceiro)]]
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| CO1 | **Verificação de CRECI: automática ou manual?** | 🟡 | Automática (API IMOBISEC, ~barato) — evita corretor sem registro no sistema. |
| CO2 | **Carteira rica ou mínima no MVP?** | 🟢 | Mínima (lista de negócios + agenda). CRM completo = Fase 2. |
| CO3 | **Taxa/split e o corretor é cliente-pagante ou parceiro de aquisição?** | 🟡 | Defaults do código (6% venda / 1 aluguel) estão certos como âncora. Split captador×vendedor 50/50 supletivo. Definir se cobra do corretor (lead-gen) ou não. |

### 📝 Fechamento → [[05 - Fechamento (transversal)]]
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| F1 | **Quão rígido travar por documento?** | 🟡 | Travar só nos **bloqueadores legais** (matrícula limpa + ITBI pago); certidões pessoais geram "score de risco" sem travar. |
| F2 | **Checklist do código está completo?** | 🟡 | Provavelmente falta **certidões de CNPJ** e **anuência do cônjuge** — validar com o Luiz. |
| F3 | **Marketplace de prestadores cartoriais** | 🟡 | Take rate **só na camada privada** (despachante/advogado). Cartório = só orquestração (comissão de cartório é **vedada por lei**). |
| F4 | **Acompanhamento externo**: como reconciliar? | 🟢 | Follow-up 7/30/45 dias (MVP); reconciliação por matrícula (Fase 2). |

### 📣 Comunicação, Suporte e Operação → [[07 - Comunicação, Suporte e Operação]]
| # | Decisão | Prio | Recomendação Douglas |
|---|---|---|---|
| O1 | **Qual BSP de WhatsApp?** | 🟡 | 360dialog (markup zero) ou Zenvia/Take Blip (faturamento/suporte BR). |
| O2 | **Quanto automatizar de comunicação no MVP?** | 🟢 | Utility (confirmações, grátis na janela) + acknowledgment instantâneo = MVP; marketing/nutrição automatizada = Fase 2. |
| O3 | **Onde cai o handoff humano e qual o SLA?** | 🟡 | Inbox corporativa do time interno; SLA no próximo horário útil, IA cobre fora dele. |
| O4 | **Quem é o time de operação no começo?** (sócios? contratados?) | 🔴 | Decisão que conecta o produto a quem vai tocá-lo. Definir o mínimo de operação que sustenta o volume do lançamento. |

---

## Parte 3 — 🧑‍⚖️ Decisões que passam pelo Luiz (jurídicas)

Agrupei as que precisam do olhar jurídico, pra ele chegar preparado:
1. **Cobrar taxa/reserva do inquilino** — juridicamente sensível (QuintoAndar sofre ação no RJ). → docs 03, 06.
2. **Nível de assinatura por ato** — aceite auditável reforçado (avançado) vale pré-cartório (STJ 2025); escritura/registro exigem **ICP-Brasil**. → doc 05 §2.
3. **Marketplace de cartório é vedado** — take rate só na camada privada (despachante). → doc 05 §3.
4. **Checklist de documentos** — adicionar certidões de CNPJ + anuência do cônjuge. → doc 05 §1.
5. **Correção factual:** o doc 05 cita teto de escritura **R$45.540**; o correto em 2026 é **R$48.630** (30 × salário mínimo R$1.621). *(Posso corrigir no doc quando vocês validarem o resto.)*
6. **LGPD na comunicação (obrigatório, não é escolha):** consentimento de WhatsApp separado do e-mail; opt-in registrado; opt-out ≤24h; WhatsApp pessoal do corretor é risco crítico → API oficial + inbox corporativa. → doc 07 §1.

---

## Sugestão de ordem da reunião (Douglas)

1. **Bater a decisão-âncora A1** (modelo de receita) — sem ela, o resto flutua.
2. **A2 + A3** (dinheiro on/off-app + catálogo MVP) — definem o escopo técnico.
3. **A4 + A5 + A6** (corretor, administração de aluguel, escopo IA) — destravam o João.
4. **Bloco do Luiz** (Parte 3) — enquanto ele está na sala.
5. **Varredura das 🟡/🟢 por fluxo** (Parte 2) — mais rápidas, muitas já têm recomendação aceitável como default.
6. **O4** (time de operação) — quem toca isso no dia a dia.

> [!tip] Como eu posso ajudar depois da reunião
> Me passa as decisões batidas (mesmo que em bullet solto) que eu **atualizo os fluxos**: troco cada "💡 Sugestão a validar" por "✅ Decidido", corrijo o teto R$48.630, e monto o **documento final de fluxos pro João** no formato que ele consegue implementar. Aí a documentação sai de "proposta" pra "spec".
