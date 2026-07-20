---
ator: Locatário (aluguel)
data: 2026-07-05
status: em construção
---

# Jornada do Locatário (Aluguel)

> 🆕 Ator inteiro a definir. Hoje o sistema **reusa a jornada de venda** só trocando rótulos (Locatário/Locador, "Aluguel mensal"). O João pediu esta jornada explicitamente.

> [!abstract] Base de pesquisa
> Sugestões abaixo vêm da pesquisa BR+US 2025-2026 em [[01 - Locacao e Corretor BR-US]] (números e fontes lá). **A Lei do Inquilinato 8.245/91 não mudou** em 2024-26 — "Nova Lei do Aluguel 2025" é clickbait.

> [!success] ✅ DECISÃO A5 — Locação (17/07/2026, Fernando)
> Locação **entra no MVP**, com **esteira própria** (sem cartório): proposta → análise de crédito → contrato → vistoria → chaves. Base: Lei do Inquilinato 8.245/91.
>
> **No MVP, sem administração:** o Cadê intermedia a locação e entrega as chaves; o proprietário administra o recorrente.
> - **Corretagem de locação:** 1 aluguel (uma vez, no fechamento).
> - **Garantias aceitas:** análise de crédito + seguro-fiança (padrão proptech; uma garantia por contrato, art. 37).
> - Reajuste anual por lista controlada (default IPCA); prazo default 30 meses; vistoria registrada.
> - O modelo de **corretor e assinatura** se aplica igual à locação.
>
> **Fase 1.5 — Administração (necessária, não bloqueia o 01/08):**
> - Taxa de administração **8,5%** ao mês.
> - **Seguro locatício obrigatório** em toda locação administrada: a **seguradora é a garantidora** (paga o proprietário no calote), então o Cadê oferece "aluguel garantido" **sem risco de crédito no balanço**.
> - Receita da locação administrada: corretagem no fechamento (1 aluguel) + administração 8,5%/mês + comissão do seguro.
> - Implementação via **PSP regulado** (cobrança recorrente + split, sem licença própria do BACEN) + **parceria com seguradora SUSEP** (garantidora).
> - 🔴 Especialista/parceria: contrato com o PSP e com a seguradora habilitada (a garantidora é ela, o Cadê é canal comissionado).

## 1. Busca e qualificação (locação) 🆕
> [!todo] ✍️ PRECISA ESCREVER
> A busca/qualificação de quem quer alugar é diferente da de quem quer comprar? (renda, garantia disponível, prazo, pets, mobiliado, etc.) Definir as perguntas que segmentam.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** sim, a qualificação de locação é diferente da de compra — ela gira em torno de **capacidade de pagar recorrente + garantia**, não de poder de compra à vista/financiamento. Os segmentadores típicos: faixa de aluguel, bairro, **renda** (regra de bolso: pacote ≤ 40% da renda, ou renda ≥ 2,5-3× o pacote), **tipo de garantia que o candidato tem** (analisar crédito / seguro-fiança / caução / fiador), prazo pretendido, mobiliado/semi/vazio, pets, nº de moradores.
> **Recomendação para o Cadê:** na busca de locação, incluir cedo a pergunta **"que garantia você tem/prefere?"** — porque ela filtra o funil (quem não passa em nenhuma garantia não avança) e já prepara a esteira. E perguntar **renda aproximada** para pré-qualificar (sem travar, só sinalizar). **[MVP]** para os filtros básicos (faixa/bairro/tipo/garantia); **[Fase 2]** a IA conversacional de calibração (mesmo status do comprador).
> **Decisão dos sócios / trade-offs:** quão "dura" é a pré-qualificação — pré-filtrar por renda reduz visitas perdidas mas adiciona fricção no topo. Sugiro leve no topo, rígida só na proposta.
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §1.1.

## 2. Proposta de locação ✍️
> [!todo] ✍️ PRECISA ESCREVER (campos já existem no código)
> Decidir: tipos de **garantia** aceitos de fato (fiador · caução · seguro-fiança · título de capitalização) e as regras/documentos por tipo; **prazo** padrão; **reajuste** (lista controlada IGPM/IPCA ou texto livre?); dia de vencimento; encargos (condomínio/IPTU quem paga).

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR) [muito disto é regra legal, não escolha]:**
> - **Garantia — uma só por contrato** (art. 37; exigir duas é contravenção). Aceitar: **caução** (máx. 3 aluguéis, art. 38 §2º), **fiança**, **seguro-fiança**, **cessão fiduciária**. O **título de capitalização** funciona como caução, não como modalidade autônoma — tratar como tal. O padrão proptech moderno é **substituir tudo por análise de crédito** (a plataforma/seguradora assume o risco).
> - **Proposta ≠ compra:** na locação aceita-se **várias propostas em paralelo** — ganha quem assina primeiro. Vale ter um recurso de **reserva (~10% de um aluguel)** que trava o imóvel. A **análise de crédito vem DEPOIS** do aceite.
> - **Reajuste:** periodicidade **mínima anual é lei**; o índice é **livre**. Recomendo **lista controlada (IPCA / IGP-M / INPC / IVAR)**, não texto livre — evita erro e padroniza. Default sugerido **IPCA** (mais estável; mercado migrou do IGP-M).
> - **Prazo:** default **30 meses** (dá direito à retomada sem motivação ao fim). Vencimento, condomínio e IPTU: campos configuráveis (condomínio/IPTU normalmente do inquilino, mas negociável).
> **Recomendação para o Cadê:** modelar garantia como **campo de tipo controlado com regras/documentos por tipo** (o código já tem os campos — falta a regra). **[MVP]** garantia + prazo + reajuste-de-lista + encargos; a reserva paga entra **[Fase 2]** (depende de processar dinheiro, ver [[06 - Planos, Serviços e Precificação]]).
> **Decisão dos sócios / trade-offs:** quais garantias o Cadê realmente aceita no MVP. Aceitar só **análise de crédito + seguro-fiança** simplifica muito (padrão proptech) vs aceitar todas (flexível, mas mais regra e mais documento). Cobrar reserva do inquilino é juridicamente sensível — passar pelo Luiz.
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §1.1-1.2.

## 3. Esteira de locação 🆕
> [!todo] ✍️ PRECISA ESCREVER
> - Documentos exigidos do **locatário** (e do fiador, se houver): quais, quando.
> - Análise de crédito/aprovação do locatário: como e por quem.
> - **Vistoria de entrada/saída** entra no fluxo? Custódia de caução?
> - Contrato de locação (assinatura) e o que significa "concluído" numa locação.
> - A locação passa pela etapa "cartorial" (conceito de venda) ou tem esteira própria?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** a esteira digital madura é: **proposta (aceitar/negociar) → aceite → análise de crédito + documentos → assinatura digital → vistoria de entrada + chaves.** Note que ela é **mais curta que a de venda e NÃO passa por cartório** (locação não tem escritura/ITBI/registro obrigatório).
> - **Documentos do locatário:** CPF, RG/RNM + selfie, comprovante de renda (3 holerites CLT ou 90 dias de extrato autônomo). Do fiador (se houver): documentos + comprovante de propriedade de imóvel quitado.
> - **Análise de crédito:** bureaus (Serasa/SPC) + ações judiciais + histórico + coerência renda×gasto, regra **renda ≥ 2,5× o pacote** (até 4 pessoas compõem). Feita pela plataforma/parceiro de garantia.
> - **Vistoria:** sim, entra — é a **prova do estado do imóvel** que sustenta descontos na saída (art. 23, III). Laudo PDF com fotos datadas, comparativo entrada×saída. **[MVP]** pelo menos registrar a vistoria (upload de laudo/fotos); vistoria digital assistida por app é **[Fase 2]**.
> - **Contrato:** assinatura eletrônica vale; coletar **2 testemunhas** para virar **título executivo** (permite despejo direto — diferencial jurídico importante). Registro em cartório = **opcional**, oferecer como serviço avulso, não travar.
> - **"Concluído" numa locação** = contrato assinado + vistoria de entrada feita + chaves entregues (não "matrícula registrada" como na venda).
> **Recomendação para o Cadê:** a locação precisa de **esteira própria**, não reusar a de venda com rótulos trocados — remover cartorial, adicionar análise de crédito e vistoria. É exatamente o que o João apontou. **[MVP]** a esteira reduzida (proposta→crédito→contrato→vistoria→chaves); custódia de caução é **[Fase 2]** (dinheiro on-app).
> **Decisão dos sócios / trade-offs:** a análise de crédito é **própria** (a Cadê assume risco, como QuintoAndar — pesado, vira produto de garantia) ou **terceirizada** a uma seguradora de fiança (mais simples, receita de comissão)? Recomendo terceirizar no início.
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §1.1-1.3.

## 4. Gestão do aluguel ativo 🆕
> [!todo] 🆕 PRECISA ESCREVER — decisão de escopo grande
> A plataforma **administra o aluguel** depois de assinado (cobrança mensal, boleto/PIX, repasse ao proprietário, reajuste anual, rescisão), ou entrega o contrato e sai? Existe papel de **imobiliária administradora**?
> → Esta decisão define se precisa construir um **módulo de cobrança recorrente** (hoje inexistente). [MVP] ou [Fase 2]?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** há **dois modelos que coexistem** (QuintoAndar oferece os dois):
> - **Administrado:** a plataforma cobra o inquilino (boleto/PIX), desconta a taxa (**8-15%**, QuintoAndar 9,3%) e repassa o **líquido** ao proprietário — e no premium **garante o repasse mesmo com inadimplência** (o grande argumento de venda). Coordena manutenção, reajuste anual, renovação/rescisão.
> - **Sem administração:** entrega o contrato e sai; proprietário gere direto; se atrasar, aciona a garantia.
> **Recomendação para o Cadê — é a decisão de escopo mais pesada da locação:**
> - **[MVP] "sem administração"** — a Cadê fecha o contrato de locação e **não** administra o recorrente. Zero módulo de cobrança recorrente (que não existe no código). Menor esforço, menor risco regulatório.
> - **[Fase 2+] administração** — exige o **módulo de cobrança recorrente + repasse líquido** (faturamento mensal, inadimplência, split via PSP) — o mesmo mini-produto de pagamentos do doc [[06 - Planos, Serviços e Precificação]]. O "aluguel garantido" adiciona ainda **risco de crédito no balanço** (a Cadê paga o proprietário do próprio bolso quando o inquilino atrasa) — é virar quase uma financeira, decisão grande.
> **Decisão dos sócios / trade-offs:** administrar é a maior fonte de **receita recorrente** da locação (e de lock-in), mas é o maior custo de engenharia + risco. Garantir o aluguel é poderosíssimo em marketing mas coloca risco de crédito no balanço. **Recomendo fortemente: locação "sem administração" no go-live**, e administração como aposta de Fase 2 quando houver volume e caixa para bancar a garantia.
> **Fontes:** [[01 - Locacao e Corretor BR-US]] §1.4 · [[06 - Planos, Serviços e Precificação]] (módulo de pagamento).
