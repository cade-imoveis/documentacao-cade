---
ator: Proprietário (anunciante)
data: 2026-07-05
status: em construção
---

# Jornada do Proprietário

> Texto ✅ = esboço original dos sócios (do `UX CADE.txt`), preservado. Pode divergir do que o código faz hoje — validar. Placeholders ✍️/🆕 = escrever.

**Tela inicial (comum aos 3 atores):** uma dobra com um ícone central de 3 partes clicáveis, representando os 3 clientes do Cadê — proprietário, comprador e corretor. Botão "meu perfil" / "já sou cliente". Todos podem estar nas 3 jornadas ao mesmo tempo: mesma tabela de usuários, e cada ação/negócio tem uma tabela de associação ligando o usuário à sua posição naquele negócio.

---

## 1. Cadastro ✅

**1ª Tela:** o proprietário se identifica com e-mail/telefone e dá o aceite no termo LGPD. Após os aceites, acessa uma tela que tem o **chat como ferramenta principal**, onde ele arrasta/carrega imagens e documentos do imóvel. Um **agente de IA** analisa os documentos e extrai dados para o cadastro do imóvel e do cliente, trata as imagens para postagem (formato, definição e uma foto com ícones que definem quartos, banheiros, garagem, metragem) e carrega vídeos. O agente é interativo: ao receber cada documento, sinaliza o "ok" com um check e evolui uma barra de conclusão. Se faltar algum arquivo, um campo/botão de fácil visualização (pop-up) pergunta o que está faltando e traz soluções para obter. Nesta tela há um ícone que direciona para o site de emissão de matrícula atualizada e outro para ajudar o proprietário a tirar as próprias fotos ou contratar serviço profissional.

**2ª Tela:** prévia das fotos tratadas e das características do imóvel. Um campo é destinado ao proprietário para colocar informações importantes (quartos, banheiros, garagem, itens de lazer e outras características que qualificam e diferenciam o imóvel — vista, posição do sol, etc.). Depois ele aperta **"gerar legenda"**, e um agente de IA faz a descrição do imóvel.

**3ª Tela — Contratação dos serviços (são 6):**
1. Usar plataforma para postar o imóvel
2. Ranquear o imóvel na plataforma (destaque)
3. Atendimento dos clientes por IA
4. Atendimento dos clientes com corretor
5. Visita com corretor
6. Jurídico/Despachante

A escolha dos serviços gera um contrato para assinar (no e-mail ou de forma mais inteligente), onde o mínimo é a **autorização de comercialização** do imóvel pelo Cadê.

> [!warning] Divergência com o código (2026-07-05)
> Hoje o cadastro é um **formulário manual** (abas + auto-CEP), não um chat com IA. Não há extração de documentos por IA, tratamento de fotos, nem geração de legenda — e o imóvel nem tem campo de descrição. Dos 6 serviços, só o **jurídico** existe (e sem preço). **Decidir o que é [MVP] até 01/08 vs. [Fase 2].**

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** o cadastro-por-chat-com-IA do UX CADE.txt **é realista hoje** — as peças existem e são baratas:
> - **Geração de descrição/legenda:** LLM a partir dos atributos do imóvel — trivial. Restb.ai gera remarks compliant em 50+ idiomas.
> - **Tratamento/realce de foto + virtual staging:** API pronta a **~US$0,30-1/imagem** (VirtualStagingAI, Collov).
> - **Detecção de atributos por foto** (quartos, piso, piscina): Restb.ai auto-popula dezenas de campos — B2B, mas existe.
> - **Extração de documentos (OCR):** de RG/CPF/comprovante é maduro (~R$1-3/consulta). **Da matrícula** é o ponto sensível — virou viável em 2025 (o **ONR lançou o IARI com o Google**), mas o estado da arte exige **revisão humana** (erro em ônus/proprietário = due diligence falha).
> **Recomendação para o Cadê — faseamento honesto:**
> - **[MVP até 01/08]:** manter o formulário, mas adicionar **campo de descrição** (hoje nem existe) + **geração de legenda por IA** + **realce/virtual staging de foto por API**. Baixo esforço, alto impacto visível.
> - **[Fase 2]:** o **chat conversacional** como interface principal + **OCR de documentos** com barra de progresso (o "agente que dá check a cada doc" do UX) + OCR de matrícula com humano no loop.
> **Decisão dos sócios / trade-offs:** o chat-first é o maior salto de UX mas o de maior esforço — dá pra entregar o *valor* (fotos tratadas + legenda) sem o *chat* no go-live, e trazer o chat depois. Definir se o MVP entrega a experiência-IA ou só o resultado-IA.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §1.3-1.4.

---

## 2. Gestão dos ativos ✅

Já cadastrados cliente e imóvel, o proprietário gerencia seus imóveis numa tela (definir nome) que mostra cada imóvel como **Card** contendo: identificação com código, imagem principal, tempo do anúncio, quantidade de views, curtidas/salvos e tempo médio de tela. Ao clicar, ele acessa:
- os **clientes de interação direta** (quero comprar / tenho interesse) e os de **interação indireta** (tempo mínimo de tela, compartilhamento, mas sem manifestar interesse direto);
- conversas com leads (IA ou corretor);
- agendamento de visitas e resultados;
- sugestão de estratégia / análise de performance.

Ponto importante: este Card **interliga proprietário, comprador e corretor**.

> [!note] No código: métricas de engajamento existem (views, visitantes únicos, tempo, temperatura), mas **não há "curtir/salvar"** nem separação lead direto/indireto. O Card = o `negócio` + participantes.

---

## 3. Esteira de aceites e contratos ✅

Ao passar da tela inicial para a 1ª tela do proprietário, ele se identifica com os dados do Google e depois dá aceite na LGPD (tratamento dos arquivos anexados) e na autorização de comercialização do imóvel, com os serviços adicionais escolhidos. Ao final da jornada: formalização de proposta e contrato de compra e venda ou locação.

---

## 4. Gestão de dados e contatos ✅

O proprietário só se comunica com possíveis compradores e corretores por uma **plataforma que não expõe números de telefone** nem dados para contatos/listas futuras. E-mails e ligações diretas: apenas com o time interno do Cadê. Todos os históricos de mensagens e transcrições de ligações ficam registrados no Card do imóvel. Os **check-ins nos imóveis** (que geram a apresentação do imóvel ao comprador) ficam registrados com hora e coordenadas no Card, mostrando o cliente vinculado.

> [!note] No código: chat anonimizado com bloqueio de troca de contato ✅. Transcrição de ligação e check-in geolocalizado ainda **não existem**.

---

## 5. Contratação de serviços (detalhar) ✍️🆕

> [!todo] ✍️ PRECISA ESCREVER — depende de `06 - Planos, Serviços e Precificação`
> A 3ª tela do Cadastro cita 6 serviços, mas falta a regra completa. Ao escrever, cubra por serviço:
> - O que é, o que o proprietário recebe, e em que etapa se contrata.
> - **Preço e forma de cobrança**: única · assinatura · por uso? (definido no doc 06)
> - Como muda a jornada de quem contrata (ex.: "com corretor" vs "só IA").
> - O que o "destaque/ranqueamento" faz de fato (como um imóvel sobe).
> Marcar cada serviço [MVP] ou [Fase 2].

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** os 6 serviços da 3ª tela não têm a mesma natureza de cobrança — separá-los é o primeiro passo. Exposição (postar/destaque) = grátis + destaque avulso ou assinatura, paga o anunciante. Atendimento/visita com corretor = % no fechamento. Jurídico = pacote fechado por uso. **Anunciar de graça é o padrão para atrair inventário**; a receita vem do destaque, dos serviços avulsos e (se for modelo transacional) da comissão.
> **Recomendação para o Cadê:** a regra completa de preço/cobrança/quem-paga de cada um dos 6 serviços está detalhada em [[06 - Planos, Serviços e Precificação]] (tabela-catálogo). Para o **MVP**, sugiro habilitar **postar (grátis) + jurídico (pacote) + destaque (avulso)**; corretor/visita/IA-avançada entram na [Fase 2] junto com a jornada do corretor. O "destaque/ranqueamento" = o imóvel sobe na ordenação da busca por período pago (como ZAP faz), **não** um algoritmo de mérito — decidir se é só posição paga ou também sinais de qualidade.
> **Decisão dos sócios / trade-offs:** ver a decisão-âncora de modelo de receita em [[06 - Planos, Serviços e Precificação]] — ela define se "postar" fica grátis para sempre ou vira gancho de conversão.
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §1, §3.5.

---

## 6. Verificação / selo do proprietário 🆕

> [!todo] 🆕 PRECISA ESCREVER
> O João citou: "se o proprietário passou no Serasa e está tudo certo, ganha um selo de verificação, e o comprador tem experiência diferente." Definir:
> - O que é verificado (identidade, Serasa, quantidade de imóveis, histórico) e como.
> - O que o **selo muda** na experiência do comprador (confiança, prioridade, filtros?).
> - É obrigatório para anunciar, ou opcional/premium?
> - [MVP] ou [Fase 2]?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** o selo funciona em **3 camadas** — (1) identidade/KYC (é pessoa/empresa real), (2) propriedade (pode legalmente anunciar aquele imóvel), (3) crédito/risco. QuintoAndar faz **selfie + documento** + análise de crédito e, no antifraude, **cruza registro do imóvel + ITBI**. O selo aumenta confiança, reduz fricção e **melhora o ranking** (verificado sobe na busca).
> **Recomendação para o Cadê:**
> - **O que verificar:** identidade (CPF + selfie/liveness, ~R$2-5/verificação via Idwall/Unico/Serpro) + propriedade (a **matrícula em nome do proprietário** — validação assistida por humano). Serasa entra no fluxo do **inquilino** (aluguel), não do proprietário.
> - **O que o selo muda:** **boost de ranking** + badge visível que dá ao comprador "experiência diferente" (exatamente o que o João citou) — mais confiança, prioridade na busca. Sugiro **não** fazer selo virar filtro obrigatório de exibição no MVP (reduz inventário).
> - **Obrigatório ou opcional:** sugiro **opcional mas fortemente incentivado** (anunciar sem selo é possível, mas o verificado ganha ranking e destaque). Pode virar gancho de conversão/serviço pago.
> - **Fase:** identidade **[MVP]** (KYC é barato e pronto); verificação de propriedade via matrícula **[Fase 2]** (depende de OCR/validação de matrícula com humano no loop).
> **Decisão dos sócios / trade-offs:** obrigatório (mais confiança, menos inventário/mais fricção) vs opcional-incentivado (mais inventário, confiança gradual). E se o selo é **grátis** (higiene da base) ou **serviço pago** (receita). Recomendo grátis a identidade, e a verificação de propriedade como serviço premium.
> **Fontes:** [[03 - IA Verificacao e Comunicacao BR-US]] §1.4-1.5.
