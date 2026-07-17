---
tema: Planos, Serviços e Precificação (a chave-mestra)
data: 2026-07-05
status: em construção
prioridade: P0 CRÍTICO
---

# ⭐ Planos, Serviços e Precificação

> **Começar por aqui.** É o maior bloqueador do João e **redefine metade das outras jornadas**. Hoje **não existe nada** de planos/preço/pagamento no código — receita é 100% off-app. Sem estas respostas, o resto fica no ar.

> [!abstract] Base de pesquisa
> As sugestões abaixo vêm da pesquisa de mercado BR+US 2025-2026 gravada em [[00 - Mercado Imobiliario Tech BR-US - Overview]]. Números e fontes estão lá. Aqui vai a leitura aplicada ao Cadê.

---

## ✅ DECISÕES DOS SÓCIOS — Modelo e Precificação (16/07/2026)

> Decididas por Fernando (CEO). Substituem as "sugestões a validar" das seções abaixo no que toca a modelo de receita, precificação e pagamento. Itens que ainda dependem de especialista contratado estão marcados 🔴. Percentuais e valores calibrados como decisão de sócio.

### Modelo de receita (A1)
Híbrido **SaaS + comissão**: cadastro grátis para captar estoque, assinaturas mensais para exposição e IA, e comissão no sucesso para o full-service. O estoque de imóveis é o fator limitante do negócio, então captação sem custo para o proprietário é a estratégia central (listar é sempre grátis).

### Catálogo e preços (P1)

**Camada 1 · Assinaturas** (dinheiro, no ato, mensais, independem de vender, pagas por cartão/PIX/boleto recorrente):

| Serviço | Preço | Observação |
|---|---|---|
| Cadastro + divulgação básica | Grátis | Isca de estoque; listar é sempre grátis |
| Ranqueamento (destaque) | R$ 159,90/mês por imóvel | Upgrade pago de posição e visibilidade |
| Atendimento por IA | R$ 59,90/mês | Custo operacional baixo, alta margem |
| Combo (ranqueamento + IA) | R$ 199,90/mês | Compromisso mínimo de 3 meses |

**Camada 2 · Comissão no sucesso** (percentual sobre o valor da venda, paga no fechamento, off-app, devida à corretora Versales):

| Modelo | Comissão | Composição interna | Regras e inclusos |
|---|---|---|---|
| Padrão (não-exclusivo) | 5% | corretor/visitas 2% + fechamento 3% | IA de atendimento inclusa sem custo; ranqueamento opcional; despachante bônus |
| Exclusividade | 4% | mesma jornada | Contrato mínimo de 3 meses; IA e ranqueamento inclusos; despachante bônus. Após 3 meses volta a 5% automático ou renova a exclusividade |

Notas importantes:
- A fatia de **2%** do módulo "corretor + visitas" é **alocação interna de receita, NÃO é o pagamento do corretor**. O que o corretor parceiro recebe é definido no contrato de parceria (linha de custo separada que impacta a margem).
- O módulo **"Fechamento"** unifica proposta/negociação + contrato de compra e venda + termo de posse.
- **Bônus despachante:** o serviço do despachante entra incluído no full-service, custeado por **parceria por volume** (custo zero para o Cadê). As **custas obrigatórias** (ITBI, emolumentos, registro) são sempre do **comprador**; o bônus é apenas o trabalho do despachante, não as taxas.

### Escopo do MVP (A3)
Decidido por Fernando (17/07/2026). O MVP entrega **captação + vitrine + primeira monetização + modelo de transação completo e pronto**, mantendo a data-meta de **01/08**. A Versales executa a operação no interim: isso é **economia de recurso** (usar o CRECI-J já existente), NÃO simplificação do sistema. A migração da operação para o Cadê fica condicionada à formalização do CRECI-J próprio + alteração do CNPJ (separação de operações).

**Entra no MVP (01/08):**

| Serviço / recurso | Observação |
|---|---|
| Cadastro grátis + divulgação | Somar campo de descrição + legenda por IA + realce de foto |
| Ranqueamento (R$ 159,90) | Posição paga na busca |
| IA de atendimento (R$ 59,90) | Resultado-IA: qualifica e responde o lead |
| Vitrine / busca do comprador | Fecha o ciclo do marketplace |
| Chat anonimizado + captação de lead | Já existe no código |
| Selo de identidade (KYC) | Opcional, com boost de ranking |
| Modelo de transação completo | Proposta + contrato (PDF) + assinatura eletrônica + fechamento; operado pela Versales no interim |
| Comissão 5% / 4% | Registrada |

**Fica para a Fase 2:**

| Item | Motivo |
|---|---|
| IA avançada (chat conversacional, OCR de docs, mapa interativo) | Maior esforço de UX |
| Verificação de propriedade (matrícula) | OCR + revisão humana |
| Jurídico/documental vendido como serviço ao cliente | Enquadramento OAB |
| Seguro-fiança, laudo | Parcerias reguladas (SUSEP/CNAI) |

**Distinção que evita confusão:** gerar **contrato em PDF + assinatura eletrônica** são recursos da plataforma e entram no MVP. Vender **assessoria jurídica** ao cliente é serviço regulado e fica na Fase 2 (enquadramento OAB).

**Dependência imediata:** entregar o modelo de transação pronto torna a **A4** (como o corretor entra num negócio) e a **P4** (mapa serviço→jornada) bloqueadores a resolver agora, pois fazem parte do fluxo de transação.

🔴 **Item societário/especialista:** formalizar o CRECI-J próprio do Cadê + alterar o CNPJ (separação de operações), com contador e advogado societário.

⚠️ **Risco de prazo sinalizado:** a camada de transação hoje é fictícia no código (contrato sem PDF, assinatura sem valor legal, corretor sem jornada). Construí-la completa até 01/08 é agressivo. Definir a versão funcional enxuta de cada etapa e validar a capacidade com o João (dev).

### Pagamento e custódia (A2)
No MVP o dinheiro passa pela plataforma **apenas nos serviços/assinaturas** (Nível 1, PSP simples). A **comissão é paga no fechamento, fora do app**. O **sinal/arras fica off-app** com contrato de arras e aceite reforçado (hash + carimbo de tempo). A **conta notarial escrow** (Provimento CNJ 197/2025) fica como opção premium de Fase 2. Não reter sinal em nome próprio, para evitar autorização prévia do Banco Central (Res. BCB 80).

### Estrutura de corretagem (A1-b) 🔴
A camada de corretagem do MVP usa o **CRECI-J e o responsável técnico da Versales** (já ativos). **Marca Cadê no front**, Versales como corretora responsável no back-office (número do CRECI no anúncio + parte no contrato de corretagem). Tratar como **ponte**: avaliar CRECI-J próprio do Cadê quando houver escala ou captação de investimento. Mitigar o ruído de marca com disclosure claro nos Termos e contrato co-branded.

### Itens que exigem especialista contratado 🔴
1. Enquadramento do serviço "jurídico/documental" (tecnologia + documental + marketplace de advogado parceiro, sem ferir a OAB / Lei 8.906/94).
2. Uso do CRECI-J da Versales pelo Cadê (contrato interco / white-label de corretagem, conformidade COFECI).
3. Contrato de parceria por volume com despachante.
4. Contrato de parceria com corretor (o repasse que define a margem real).
5. Contrato de arras + fluxo de taxa de reserva no cartão (conformidade CDC) e, na Fase 2, integração com escrow notarial.
6. Parceria com corretora de seguros habilitada na SUSEP para seguro-fiança (Fase 2).

> **Base jurídica das decisões:** Lei 8.906/94 (OAB), Lei 6.530/78 (CRECI), Lei 10.169/2000 (cartório), normas SUSEP, Res. BCB 80, Provimento CNJ 197/2025, Código Civil (arras arts. 417 a 420; corretagem e exclusividade arts. 722 a 729). Lembrete: o Luiz é o **responsável** jurídico, não o especialista técnico; o mérito fino cabe a especialista contratado.

---

## Perguntas a decidir

### O que a Cadê vende
> [!todo] ✍️ PRECISA ESCREVER
> Liste os serviços (a 3ª tela do proprietário cita 6: postar, destaque/ranqueamento, atendimento por IA, atendimento por corretor, visita com corretor, jurídico/despachante — e há também cartorial, avaliação, fotografia). O que entra no catálogo?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR / US):** o mercado separa nitidamente **duas fontes de receita** que a Cadê está misturando na mesma tela: (1) *serviços de exposição/mídia* (anunciar, destaque) — modelo portal, cobra o anunciante; (2) *serviços do negócio* (corretagem, jurídico, cartório, fotografia, laudo) — modelo transacional/avulso. QuintoAndar vende (2); Grupo OLX/ZAP vende (1); todos vendem serviços avulsos por fora (foto, seguro-fiança, laudo).
> **Recomendação para o Cadê:** organizar o catálogo em **3 famílias**, não numa lista solta de 6:
> - **Exposição** — postar o imóvel [MVP] · destaque/ranqueamento [MVP ou Fase 2].
> - **Atendimento & venda** — atendimento por IA [MVP] · atendimento/visita com corretor [Fase 2, depende da jornada do corretor] · gestão da esteira [MVP].
> - **Serviços avulsos (à la carte, margem alta, baixo esforço)** — jurídico/despachante [MVP, já existe no código] · cartorial [Fase 2] · fotografia/tour 3D [Fase 2] · avaliação/laudo [Fase 2] · seguro-fiança [Fase 2, locação].
> **Decisão dos sócios / trade-offs:** quais entram até 01/08. Sugiro **MVP mínimo vendável = postar + jurídico + (talvez) destaque**; o resto entra depois sem travar o go-live. O erro a evitar é o João ter que codar os 6 genéricos agora.
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1-3.

### Preço e forma de cobrança
> [!todo] ✍️ PRECISA ESCREVER — a dúvida nº1 do João
> Para **cada** serviço: **preço** e **forma de cobrança** — **única** (paga uma vez), **assinatura** (recorrente mensal), ou **por uso** (paga quando usa)?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** cada família tem uma forma de cobrança natural — não se cobra tudo do mesmo jeito:
> - **Exposição → assinatura mensal ou por-uso** (ZAP PF R$77-80/mês com destaque 6 meses; profissional R$225/mês+). Destaque avulso PF R$20-150.
> - **Corretagem → % única no fechamento** (QuintoAndar venda até 6%; mercado 5-6%). Locação: administração recorrente 9,3%/mês + corretagem = 1 aluguel (uma vez).
> - **Serviços avulsos → preço fixo por uso** (foto R$200-500; laudo R$400-1.500; jurídico pacote fechado; seguro-fiança 8-16%/ano do aluguel).
> **Recomendação para o Cadê:** montar a **tabela-catálogo** (ver "Entregável" no fim). Faixas de mercado como ponto de partida — **os valores exatos são aposta de sócio, não pesquisa**. Ancorar a comissão de venda em **≤6%** (teto de mercado/CRECI); decidir se a Cadê entra abaixo disso como diferencial (EmCasa se posiciona como "mais barata", mas não publica número).
> **Decisão dos sócios / trade-offs:** o número. Comissão cheia (~6%) maximiza receita/transação mas exige entregar valor de corretora full-service; comissão baixa (3-4%) + serviços avulsos é volume + upsell. Assinatura de exposição dá receita recorrente previsível mas exige inventário grande para valer a pena.
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1, §3.5.

### Quem paga
> [!todo] ✍️ PRECISA ESCREVER
> Quem paga cada coisa: proprietário, comprador/locatário ou corretor?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** o padrão é claro e quase universal:
> - **Venda → o vendedor/proprietário paga** a comissão. O comprador não paga corretagem no BR (diferente dos EUA pós-NAR, que agora tem buyer-fee — **não transferível**).
> - **Locação → o proprietário paga** administração + corretagem. O inquilino só paga seguro-fiança (se optar) e, em alguns modelos, uma "taxa de serviço" — **mas cobrar o inquilino é juridicamente contencioso** (QuintoAndar sofre ação no RJ).
> - **Exposição/destaque → o anunciante paga** (proprietário PF ou corretor).
> **Recomendação para o Cadê:** seguir o padrão — **proprietário/vendedor é o pagador principal**. Evitar cobrar o comprador (fricção que nenhum concorrente BR cobra) e ter **cuidado jurídico com qualquer cobrança do inquilino** (passar pelo Luiz antes).
> **Decisão dos sócios / trade-offs:** se quiser cobrar o corretor (modelo lead-gen tipo Zillow Premier Agent — agente compra leads), é uma linha de receita adicional, mas depende da jornada do corretor existir (Fase 2). Decidir se corretor é *cliente pagante* ou *custo de aquisição*.
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1, §2 (NAR).

### Gratuidade e modelo de receita
> [!todo] ✍️ PRECISA ESCREVER
> - **Anunciar é grátis?** (A home diz "anuncie grátis".) Freemium? Cobra na conversão?
> - **Receita principal**: comissão sobre venda/locação? assinatura de corretor/imobiliária? fee por pacote? cobrança por lead? destaque pago? (pode ser combinação)

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR/US):** o **freemium é o padrão** — grátis para popular inventário e gerar leads; paga na conversão/serviço/exposição. Grátis: anunciar (fotos, preço, descrição), busca, roteamento de contato, AVM. Pago: destaque, corretagem, serviços avulsos, e-sign/contrato, processamento de pagamento. Nos grandes portais, **anunciar deixou de ser grátis para o profissional** — mas continua grátis para o proprietário PF em opções básicas.
> **Recomendação para o Cadê — 3 modelos possíveis (escolher 1 como âncora, combinar depois):**
> | Modelo | Receita principal | A favor | Contra |
> |---|---|---|---|
> | **(A) Transacional** (tipo QuintoAndar) | comissão de venda/locação | alinha receita ao sucesso; anunciar grátis atrai inventário | receita só quando fecha; exige entregar o fechamento; ciclo longo |
> | **(B) Portal/assinatura** (tipo ZAP) | assinatura + destaque do anunciante | receita recorrente previsível desde o dia 1 | exige volume de anunciantes; não monetiza o negócio em si |
> | **(C) Híbrido serviços** | avulsos (foto/jurídico/laudo/seguro) + destaque, comissão opcional | margem alta, baixo esforço técnico, começa já | receita fragmentada; menos "lock-in" |
> **Minha leitura de COO:** para um go-live em 01/08 com o sistema que já existe, **(C) + anunciar grátis** é o caminho de menor esforço e menor risco — vende serviços avulsos num checkout simples enquanto a comissão transacional (A) amadurece. (A) é o modelo de maior valor no longo prazo, mas depende da esteira de fechamento estar redonda. (B) só faz sentido com inventário grande.
> **Decisão dos sócios / trade-offs:** qual é a **âncora de receita**. Isso define o produto — não dá para adiar. Recomendo cravar a âncora antes de o João codar telas de plano.
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1, §3.5.

### O dinheiro passa pela plataforma?
> [!todo] ✍️ PRECISA ESCREVER — decisão que define esforço técnico grande
> O pagamento passa pela Cadê (gateway/PIX/cartão) ou é sempre off-app? → se passa, é preciso **construir um módulo de pagamento/faturamento do zero** (hoje inexistente).

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** os portais **não tocam no dinheiro** (off-app); os transacionais de locação **sim** (QuintoAndar cobra o inquilino e garante repasse ao proprietário). Quem processa dinheiro usa um PSP regulado (Asaas/Iugu/Pagar.me) com **split** — não vira banco. Custo: PIX ~R$2, cartão ~3%.
> **Recomendação para o Cadê — decisão em 2 níveis, não 1:**
> - **Nível 1 — cobrar serviços avulsos (foto, jurídico, destaque):** um checkout simples com **1 PSP, sem split**. Esforço baixo. **[MVP viável]**. O dinheiro do serviço passa, mas é trivial.
> - **Nível 2 — intermediar o negócio (sinal/arras, aluguel recorrente, split de corretagem):** aí sim é **construir um mini-produto de pagamentos** (KYC de sellers, motor de split, ledger/conciliação próprio, faturamento recorrente, custódia de sinal, chargeback). Semanas-meses. **[Fase 2+]**.
> **Fronteira regulatória a NÃO cruzar sem decisão consciente:** enquanto o dinheiro fica na conta de um PSP regulado, a Cadê **não precisa de licença própria**. No momento em que ela **mantiver saldo de terceiros em nome próprio**, cai na Res. BCB 80 (alterada 09/2025) e precisa de **autorização prévia do BC** — que agora é obrigatória *antes* de operar.
> **Decisão dos sócios / trade-offs:** off-app = simples, rápido, sem risco regulatório, mas perde a "cola" financeira e o float. On-app = lock-in e novas receitas (float, garantia, antecipação — o caminho da Loft), mas é engenharia pesada + peso regulatório. **Recomendo Nível 1 no MVP, Nível 2 só quando o volume justificar.**
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §3.1-3.4.

### Como o serviço muda a jornada
> [!todo] ✍️ PRECISA ESCREVER
> O nível de serviço contratado muda os passos que o usuário vê (ex.: quem tem "atendimento por corretor" vs. quem tem só "IA"; quem tem jurídico vs. quem segue sozinho). Mapear essas variações — é o que o João precisa para não fazer código genérico.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** as plataformas transacionais **ramificam a jornada por nível de serviço** — QuintoAndar "com" vs "sem administração" muda todo o fluxo de repasse; pacote com corretor vs self-service muda quem faz as visitas. O serviço contratado é uma *flag* que liga/desliga etapas.
> **Recomendação para o Cadê:** modelar o serviço como **um conjunto de flags no negócio** que o código já entende (o `negócio` + `papéis` da esteira as-built suportam isso). Duas ramificações principais a definir:
> - **Atendimento IA vs Corretor:** só-IA = comprador conversa com o agente, agenda visita self-service; com-corretor = entra um papel `corretor` no negócio, ele conduz visita e negociação (depende da jornada do corretor, [[04 - Corretor (Parceiro)]]).
> - **Com jurídico vs sem:** com = a esteira ganha a etapa de documentos/contrato assistida pelo despachante Cadê; sem = as partes seguem para "acompanhamento externo".
> **Decisão dos sócios / trade-offs:** definir o **mapa serviço→etapas** é o que destrava o João. Recomendo os sócios preencherem isso junto com a jornada do corretor (Fase 2), porque as duas se amarram.
> **Fontes:** [[10 - Dossie do Sistema (as-built)]] (esteira/papéis) · [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1.

### Entregável sugerido
Uma **tabela**: serviço · o que é · preço · forma de cobrança · quem paga · [MVP]/[Fase 2].

> [!example] 💡 Rascunho do Douglas — tabela-catálogo para os sócios editarem — A VALIDAR
> Preços = **faixas de mercado** (ponto de partida, não recomendação de número). Sócios cravam o valor.
>
> | Serviço | O que é | Faixa de mercado (ref.) | Forma de cobrança | Quem paga | Fase |
> |---|---|---|---|---|---|
> | Postar imóvel | anúncio na plataforma | grátis (isca de inventário) | — | — | MVP |
> | Destaque/ranqueamento | subir o imóvel na busca | R$ 20-150 (PF) / plano PJ | por uso ou assinatura | anunciante | MVP/F2 |
> | Atendimento IA | agente conversa/qualifica lead | incluso? | — | — | MVP |
> | Atendimento + visita c/ corretor | corretor conduz | % da comissão | no fechamento | proprietário | F2 |
> | Jurídico/despachante | contrato + documentação | pacote fechado | única/por uso | proprietário | MVP |
> | Cartorial | ITBI, escritura, registro | custas + serviço | por uso | comprador (custas) | F2 |
> | Fotografia/tour 3D | mídia profissional | R$ 200-800 | única/por uso | proprietário | F2 |
> | Avaliação/laudo | AVM grátis; laudo pago | laudo R$ 400-1.500 | por uso | quem pede | F2 |
> | Seguro-fiança | garantia s/ fiador (locação) | 8-16%/ano do aluguel | recorrente | inquilino | F2 |
> | Comissão de venda | corretagem no fechamento | ≤6% | única (%) | vendedor | ? |
> | Administração de aluguel | gestão + repasse | 8-12% (mercado) | recorrente (%) | proprietário | ? |
>
> As três últimas linhas (comissão/administração) só se aplicam se o Cadê adotar o **modelo transacional (A)** — é a decisão-âncora acima.
