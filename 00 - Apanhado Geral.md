---
tema: Apanhado geral — índice de ação (decisões + desenhos de fluxo)
data: 2026-07-12
status: para o Fernando percorrer
---

# 📋 Apanhado Geral — o que falta fazer

> [!info] Como usar
> Lista de **tudo o que falta definir**, uma linha por item, com o ponteiro para o documento detalhado (que já traz a sugestão do Douglas + o trade-off). Percorra na ordem: **decisões-âncora → jurídico → resto**. Quem detalha cada decisão é o `08 - Resumão`; quem detalha cada fluxo são os docs `01`–`07`. Comece pelo [[08 - Resumão - Decisões para a Reunião]] se quiser o contexto de cada uma.
> **Legenda:** 🔴 destrava o dev · 🟡 regra de negócio · 🟢 escopo (MVP × Fase 2) · ⚖️ jurídico (Luiz).

---

## 1. Decisões-âncora (resolver primeiro) 🔴

- **A1 — Modelo de receita** (transacional × portal × híbrido); sugerido: híbrido + anunciar grátis → **06**, resumão §A1
- **A2 — O dinheiro passa pela plataforma?** (Nível 1 avulsos × Nível 2 intermediar); sugerido: Nível 1 no MVP → **06**, **05 §4**
- **A3 — Catálogo do MVP** (o que entra até o go-live); sugerido: postar + jurídico + destaque → **06**, **01 §5**
- **A4 — Como o corretor entra num negócio** (atribuição × pool × convite); sugerido: atribuição + convite → **04 §2**
- **A5 — Administrar o aluguel ou não** (sem adm × administrado + garantido); sugerido: sem administração no go-live → **03 §4**
- **A6 — Escopo de IA no MVP** (resultado-IA × experiência-IA); sugerido: resultado-IA (foto/legenda/busca) → **01 §1**, **02 §1/§3**

## 2. Jurídico — para o Luiz ⚖️

- **J1 — Cobrar taxa/reserva do inquilino?** (sensível; QuintoAndar sofre ação) → **03**, **06**
- **J2 — Nível de assinatura por ato** (aceite reforçado pré-cartório × ICP-Brasil na escritura/registro) → **05 §2**
- **J3 — Marketplace de cartório é vedado** (take rate só na camada privada/despachante) → **05 §3**
- **J4 — Checklist de documentos** (falta certidões de CNPJ + anuência do cônjuge) → **05 §1**
- **J5 — Correção factual** (teto da escritura obrigatória = R$48.630 em 2026, não R$45.540) → **05**
- **J6 — LGPD na comunicação** (opt-in de WhatsApp separado; WhatsApp pessoal do corretor = risco) → **07 §1**

## 3. Decisões por fluxo

### Planos, Serviços e Preço → **06**
- **P1 — Preço de cada serviço** (o número; aposta de sócio; faixas de mercado dadas) 🟡
- **P2 — Comissão de venda** (manter ~6% × entrar abaixo como diferencial) 🟡
- **P3 — Quem paga cada coisa** (proprietário/vendedor; não cobrar comprador) 🟡
- **P4 — Mapa serviço → etapas** (como o serviço muda a jornada) 🔴

### Proprietário → **01**
- **PR1 — Selo obrigatório ou opcional?** (sugerido: opcional incentivado) 🟡
- **PR2 — Selo grátis ou pago?** (sugerido: identidade grátis, propriedade premium) 🟡
- **PR3 — Faseamento do selo** (identidade MVP, propriedade Fase 2) 🟢

### Comprador → **02**
- **C1 — Busca conversacional** (chat × filtro + ranking semântico) 🟢
- **C2 — Mapa interativo** (MVP × Fase 2; "amei" no MVP) 🟢
- **C3 — Qualificação obrigatória para avançar?** (leve no interesse, rígida na visita) 🟡
- **C4 — Quando liberar o endereço exato** (após validação de documento) 🟡
- **C5 — Múltiplas propostas na compra** (exclusiva/vinculante × várias) 🟡
- **C6 — Anti-desintermediação** (manter bloqueio; não investir em máscara) 🟢

### Locatário (Aluguel) → **03**
- **L1 — Garantias aceitas no MVP** (sugerido: crédito + seguro-fiança; uma por contrato é lei) 🟡
- **L2 — Análise de crédito própria × terceirizada** (sugerido: terceirizar no início) 🟡
- **L3 — Dureza da pré-qualificação** (leve no topo, rígida na proposta) 🟢

### Corretor (Parceiro) → **04**
- **CO1 — Verificação de CRECI** (automática por API × manual) 🟡
- **CO2 — Carteira** (mínima MVP × CRM completo Fase 2) 🟢
- **CO3 — Taxa, split e papel do corretor** (defaults 6%/1 aluguel; split 50/50; cliente × parceiro) 🟡

### Fechamento → **05**
- **F1 — Rigidez de travamento por documento** (só bloqueadores legais) 🟡
- **F2 — Checklist está completo?** (falta CNPJ + cônjuge) 🟡
- **F3 — Marketplace de prestadores** (take rate só camada privada; cartório = orquestração) 🟡
- **F4 — Acompanhamento externo** (follow-up MVP × reconciliação por matrícula Fase 2) 🟢

### Comunicação, Suporte e Operação → **07**
- **O1 — Qual BSP de WhatsApp** (360dialog × Zenvia/Take Blip) 🟡
- **O2 — Quanto automatizar no MVP** (utility + acknowledgment MVP; marketing Fase 2) 🟢
- **O3 — Handoff humano + SLA** (inbox corporativa; próximo horário útil) 🟡
- **O4 — Quem é o time de operação no começo** (sócios × contratados) 🔴

---

## 4. Desenhos de fluxo — o que escrever/validar

> Status: ✅ esboçado (do UX original, revisar) · ✍️ a validar e detalhar · 🆕 a desenhar do zero. Cada um tem sugestão do Douglas no doc.

### Proprietário → **01**
- Cadastro (chat-IA / OCR / fotos / legenda) ✅ (código é formulário — decidir MVP)
- Gestão dos ativos (cards, métricas) ✅
- Esteira de aceites e contratos ✅
- Gestão de dados e contatos (chat anonimizado) ✅
- Contratação de serviços (os 6 serviços) ✍️
- Verificação / selo do proprietário 🆕

### Comprador → **02**
- Segmentação e leitura (busca IA) ✅
- Identificação ✅
- Cards e mapa (ranqueamento/matching) ✅
- Interesse → negociação (regras de proposta/visita) ✍️
- Esteira de compra (do match ao fechamento) ✍️

### Locatário (Aluguel) → **03** — jornada inteira nova
- Busca e qualificação (locação) 🆕
- Proposta de locação (garantias, reajuste, prazo) 🆕
- Esteira de locação (crédito → contrato → vistoria) 🆕
- Gestão do aluguel ativo (cobrança/repasse/renovação) 🆕

### Corretor (Parceiro) → **04** — jornada inteira nova
- Cadastro / onboarding (CRECI) 🆕
- Entrada num negócio (distribuição de lead) 🆕
- Carteira (imóveis + leads) 🆕
- Comissão e repasse ✍️

### Fechamento (transversal) → **05**
- Documentos e due diligence ✍️
- Contrato e assinatura ✍️
- Fluxo cartorial (só venda) ✍️
- Pagamento / sinal ✍️
- Acompanhamento externo ✍️

### Planos, Serviços e Precificação → **06** — a chave-mestra
- Catálogo, preço, forma de cobrança, quem paga, dinheiro-na-plataforma, mapa serviço→jornada — tudo a definir ✍️

### Comunicação, Suporte e Operação → **07**
- Comunicação / Hermes (mensagens, WhatsApp, cadência) 🆕
- Suporte e handoff humano ✍️
- Operação Cadê (time interno, admin) 🆕

---

## 5. Mapa dos documentos desta pasta

- **00 - Apanhado Geral** (este) — índice de ação.
- **00 - README - Como usar** — como a pasta funciona e a legenda.
- **01–07** — um fluxo por ator/tema, com placeholders + sugestão do Douglas a validar.
- **08 - Resumão** — todas as decisões consolidadas com opções e trade-offs (o mais denso).
- **09 - Apresentacao Reuniao Socios.html** — deck de apoio à reunião (abrir no navegador).

> A base de pesquisa (BR + EUA) que fundamenta cada sugestão vive no vault do Douglas (`06 - Conhecimento/Mercado Imobiliario Tech BR-US/`, 4 dossiês) — fora deste repo.
