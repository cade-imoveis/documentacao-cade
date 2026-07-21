---
ator: Comprador (venda)
data: 2026-07-05
status: em construção
---

# Jornada do Comprador

> Texto ✅ = esboço original dos sócios (do `UX CADE.txt`). Placeholders ✍️/🆕 = escrever.

---

> [!success] ✅ DECISÃO C1-C6 — Jornada do Comprador (17/07/2026, Fernando)
> - **C1 Busca:** filtro + **ranking semântico (pgvector)** no MVP; chat conversacional na Fase 2.
> - **C2 Cards/mapa:** **amei/salvar** + lista de seleção + destaque pago no MVP; **mapa interativo** e reranking comportamental na Fase 2.
> - **C3 Qualificação:** leve no "tenho interesse"; **validação de documento exigida para a visita** (não trava o topo do funil).
> - **C4 Endereço:** a vitrine mostra **localização aproximada** (bairro + ponto de referência, ex.: "perto do Praia Clube, Bairro Tubalina"); o **endereço exato e mais informações** são liberados quando o cliente entra no **fluxo de cadastro + validação**. Transparência da região + captura do lead qualificado.
> - **C5 Propostas:** a proposta **não trava** o imóvel (proposta ≠ contrato de compra e venda). O sistema só **bloqueia com contrato assinado**; o proprietário pode, por conta própria, parar de considerar outras propostas.
> - **C6 Anti-desintermediação:** manter o bloqueio de contato (higiene), **sem investir em máscara perfeita**; a retenção real vem do valor on-platform (contrato, selo, garantia) e do roteamento pelo Cadê.

## 1. Segmentação e leitura ✅

**1ª Tela:** após a tela inicial dos clientes, ao se identificar como comprador, começa a jornada de **qualificação da busca**. A IA interage com perguntas que direcionam a pesquisa. Ex.:
> Vamos começar. Você quer comprar ou prefere alugar agora? etc.
> Selecione do mais importante para o menos importante (gamificação):
> a) Construção moderna · b) Tamanho da área externa · c) Localização

*Pensar sobre adequar a comunicação para cada perfil comportamental.*

> [!note] No código: existe **qualificação pós-interesse** (urgência/prioridades/temperatura), mas **não** a IA conversacional que segmenta a busca **antes** de mostrar resultados. Definir se essa IA de busca é [MVP] ou [Fase 2].

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** a **busca conversacional com IA virou tabela competitiva** — Zillow tem desde 2023, hoje dentro do ChatGPT; Realtor.com e Redfin seguiram. O padrão técnico: **LLM extrai filtros da frase** ("apê perto de escola com quintal até R$X") → **busca semântica/vetorial** + filtros estruturados → refina por perguntas → explica tradeoffs. É construível **hoje** no stack do Cadê.
> **Recomendação para o Cadê:**
> - **[MVP realista]:** um LLM que converte a frase do comprador em **filtros JSON** aplicados nos filtros que já existem no banco, + **embeddings (pgvector no Supabase)** sobre a descrição do anúncio para ranking semântico. Isso entrega 80% da mágica do UX CADE.txt com custo baixo. As perguntas de calibração ("é isso que procura?") saem naturalmente do chat.
> - **[Fase 2]:** memória multi-turno, isócronas de "perto do centro/escola", embeddings de foto, reranking personalizado por comportamento.
> - **Guardrail obrigatório:** a IA de busca não pode discriminar por perfil protegido (equivalente ao Fair Housing dos EUA / anti-discriminação BR) — LLM com grounding, proibido inventar imóvel.
> **Decisão dos sócios / trade-offs:** entregar a **busca conversacional** já no MVP (grande diferencial, esforço médio) ou começar com filtro tradicional + só o ranking semântico por trás. Recomendo o segundo como MVP e o chat como Fase 2 — o valor (resultado relevante) vem antes da interface (chat).
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §1.1-1.2.

---

## 2. Identificação ✅

Identificação do cliente pelo cadastro do Google, iCloud, etc.

---

## 3. Cards e mapa ✅

**1ª Tela:** após definir a busca e se identificar, a próxima tela entrega a **seleção de imóveis baseada no perfil da busca**. O resultado deve direcionar e segmentar — não apresentar uma infinidade de opções que gera indecisão.
- A cada X opções, uma **pergunta de calibração**: "É isso mesmo que procura? Mudaria algo no filtro?"
- O imóvel é apresentado em um **card** cuja disposição de informações é otimizada (com ajuda da IA) para dar mais espaço à foto; a miniatura tem um botão de "passar" para o próximo sem entrar no detalhe.
- **Mapa interativo** mostra a quantidade de opções; ao interagir/dar zoom, muda a relação de imóveis por região.
- A disposição dos imóveis sofre a ação do nosso **ranqueamento** (destaques).
- Ao passar por um card de interesse, o comprador pode **selecionar/flegar** o imóvel; ao final, a tela vira uma **relação da seleção**, para ele não ficar voltando/divagando.

**2ª Tela:** com a seleção na tela, simplificamos a jornada de escolha e captamos o **perfil de consumo** pelo comportamento da seleção. A IA analisa esse comportamento para calibrar sugestões e ficar mais eficiente (mais tempo de tela, mais interação, mais chance de finalizar com experiência positiva). *"Nossa IA não é um corretor que não escuta e entrega o que o cliente não quer."* Botão **amei/salvar** disponível ao acessar o imóvel, montando a lista de imóveis com que ele interagiu (perfil de consumo).

No **detalhe do imóvel**, o comprador pode: agendar uma visita, fazer uma proposta (caso o proprietário tenha liberado), conversar com o responsável (proprietário, IA ou corretor). A ação fica registrada na agenda do e-mail de cadastro, com marcação automática e **lembrete um dia antes por WhatsApp** ou outro meio indireto.

A visita é feita, mas exige **validação de documento do comprador** (camada de segurança para o contato com corretor/proprietário). Ao chegar ao endereço, a IA pode interagir com o comprador para obter a **localização** e vincular a visita. No ato da visita, o comprador pode carregar uma **barra de satisfação** ou apertar o botão **Match** para gerar a esteira de compra (envio de contrato para efetivação da etapa). Se não gostou, uma nova sequência de perguntas calibradoras segmenta outros imóveis.

O **ReMKT** para quem não finalizou é importante e deve ser aquecido por uma cadência de mensagens. Todas as interações geram relatório de perfil comportamental e preferências. Toda a experiência com os imóveis alimenta o histórico do imóvel (performance para o responsável) e o perfil do usuário (tendências de consumo: idade, classe, metragem, quartos, localização, ticket, etc.). O cliente da esteira de compra é direcionado ao **jurídico/despachante** para a documentação do contrato de compra e venda.

*Sobre os dados: todos seguem a lógica — o que aconteceu, por que aconteceu, o que vai acontecer, o que fazer? Data driven, para não haver "vale da morte" dos dados. Gamificação de disciplina de atendimento/cadastro.*

> [!note] No código: busca é filtro tradicional (sem IA de calibração/mapa interativo/ranqueamento); "amei/salvar" não existe; agendar visita/proposta/chat existem; validação de doc pré-visita, check-in, botão Match, barra de satisfação, ReMKT automático e relatórios comportamentais **não existem**. Muita coisa aqui é **[Fase 2]** — priorizar.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** o "ranqueamento que calibra por comportamento" do UX é **matching estilo Netflix** — sinais positivos (**save/amei**, contato, agendar visita), engagement (**dwell time**, fotos vistas, scroll) e negativos (**passar/back rápido**). O Cadê **já coleta métricas de engajamento** (views, tempo, temperatura) — falta o **"amei/salvar"** (que é o sinal mais forte) e o motor que usa isso pra reordenar.
> **Recomendação para o Cadê — priorização dentro deste §3 (que é o mais ambicioso do doc):**
> - **[MVP]:** implementar o **"amei/salvar"** (barato, é o sinal de ouro) + a **lista de seleção** ("a tela vira a relação da seleção") + **ranqueamento por destaque pago** (ligado ao doc [[06 - Planos, Serviços e Precificação]]).
> - **[Fase 2]:** o **mapa interativo** com densidade por zoom, o **card otimizado por IA**, e o **reranking personalizado** que aprende do comportamento (o "nossa IA não é um corretor que não escuta").
> - O "perfil de consumo" que o UX descreve = os embeddings de comportamento; começa simples (histórico de saves/filtros) e evolui.
> **Decisão dos sócios / trade-offs:** o mapa interativo e o reranking comportamental são caros; o "amei" + destaque pago entregam a espinha dorsal cedo. Definir se o mapa é MVP (é muito citado no UX) ou Fase 2.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §1.1.

---

## 4. Interesse → negociação (consolidar a regra) ✍️

> [!todo] ✍️ PRECISA ESCREVER — é a jornada mais pronta no código; falta cravar a regra
> Do "tenho interesse" até o "match". Decidir:
> - A qualificação é **obrigatória** para avançar (hoje não trava nada)?
> - Quem **inicia a visita** — só o anunciante sugere (como hoje) ou o comprador também pede?
> - Quem confirma que a visita **aconteceu**? Precisa de confirmação do comprador / tratar no-show?
> - **Múltiplas propostas**: há limite de contrapropostas? proposta expira? aceitar uma recusa as outras?
> - **Anti-desintermediação**: bloquear a mensagem (hoje) ou gravar mascarada? Há punição a quem insiste?
> - Quando o **endereço exato** é liberado — basta ter interesse (hoje) ou só após visita/qualificação?
> Marcar [MVP]/[Fase 2].

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado — o achado contra-intuitivo (estudo Airbnb/BU 2022):** **mascarar/bloquear contato tem impacto quase nulo** na desintermediação. Partes motivadas contornam (encodam o número na mensagem). Máscara = higiene, **não** a defesa. O que **retém de verdade**: valor que só existe on-platform (garantia, seguro, contrato, orquestração), reputação atrelada ao ranking, e baixa fricção pra fechar dentro.
> **Recomendação para o Cadê — respondendo cada ponto:**
> - **Anti-desintermediação:** manter o bloqueio de contato que já existe (é higiene barata, ✅), mas **não investir pesado em mascaramento perfeito**. A retenção real vem de amarrar o **valor** (jurídico, selo, garantia, contrato digital) à plataforma. Punição a quem insiste = fricção que irrita; preferir incentivo a ficar.
> - **Qualificação obrigatória para avançar:** sugiro **leve** — não travar o "tenho interesse", mas **exigir qualificação/validação de documento antes da visita** (o UX já pede "validação de documento do comprador" como camada de segurança). Isso filtra sem matar o topo do funil.
> - **Quem inicia a visita:** ambos (anunciante sugere **e** comprador pede) — hoje só o anunciante; abrir pro comprador aumenta conversão (speed-to-lead).
> - **Confirmação de visita / no-show:** usar o **check-in geolocalizado** do UX (a IA capta a localização no ato) como confirmação; tratar no-show movendo o lead de volta pra nutrição.
> - **Múltiplas propostas:** na **compra**, proposta tende a ser mais exclusiva/vinculante (com sinal); definir se aceita várias em paralelo ou uma trava as outras. (Na locação, o padrão é aceitar várias — ver [[03 - Locatário (Aluguel)]] §2.)
> - **Endereço exato:** liberar **após qualificação/validação de documento** (não só "ter interesse"), como camada de segurança + anti-bypass leve.
> **Recomendação de fase:** **[MVP]** bloqueio de contato (existe) + validação de doc pré-visita + visita iniciável pelos dois lados; **[Fase 2]** check-in geolocalizado, detecção NLP de troca de contato, botão Match/barra de satisfação.
> **Decisão dos sócios / trade-offs:** quão rígida a qualificação e quando liberar o endereço — segurança/anti-bypass vs fricção. Recomendo leve no interesse, rígido na visita.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §1.6.

---

## 5. Esteira de compra (do match ao fechamento) ✍️

> [!todo] ✍️ PRECISA ESCREVER — puxa o doc `05 - Fechamento`
> O que o comprador vê e faz do "match" até assinar: documentos exigidos dele, jurídico/despachante, contrato, pagamento/sinal, cartório. Ver `05 - Fechamento (transversal)` para as regras compartilhadas. Decidir o que o comprador enxerga em cada etapa e o que é obrigatório dele.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** a esteira de compra do comprador é a **jornada de fechamento** — as regras (documentos, assinatura, cartório, sinal, ITBI) estão consolidadas em [[05 - Fechamento (transversal)]], preenchido na Fase 3. Aqui vale só o **recorte do que o comprador vê/faz**:
> - **Documentos do comprador:** RG/CPF, estado civil (+ cônjuge), comprovante de residência; renda **só se financiar**. Menos pesado que o do vendedor.
> - **O comprador é quem paga ITBI + custas** (~3-6% do imóvel) — mostrar isso cedo, é surpresa clássica que derruba negócio.
> - **Sinal/arras:** se houver, o comprador paga na **proposta vinculante/promessa** (antes da escritura). Deixar explícito se é confirmatória (desistiu, perde) ou penitencial.
> - **"Concluído" pro comprador = ele virou dono na matrícula** (registro), não a assinatura. A jornada dele deve mostrar o status real até o registro.
> **Recomendação para o Cadê:** a tela do comprador na esteira = **um checklist do "que falta de você" + status do negócio** (com o marco final sendo o registro). **[MVP]** o recorte de documentos do comprador + transparência de custos (ITBI/custas) + geração/assinatura do contrato; integração cartorial = [Fase 2]. As regras completas e as decisões abertas estão em [[05 - Fechamento (transversal)]].
> **Decisão dos sócios / trade-offs:** ver as decisões do doc 05 (nível de assinatura, o que trava, marketplace de prestadores). Aqui a decisão específica é **quanto do fechamento o comprador faz sozinho no app vs com o despachante/jurídico Cadê**.
> **Fontes:** [[02 - Fechamento e Cartorio BR]] · [[05 - Fechamento (transversal)]].
