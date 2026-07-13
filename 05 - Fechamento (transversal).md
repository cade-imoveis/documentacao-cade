---
tema: Fechamento (transversal — puxado por comprador e locatário)
data: 2026-07-05
status: em construção
---

# Fechamento (transversal)

> A **estrutura** existe no código e é sólida; várias **execuções são fictícias** (contrato sem PDF real, "assinatura" sem valor legal, PIX = upload de comprovante, comissão informativa). Aqui se define a regra real.

> [!abstract] Base de pesquisa
> Sugestões deste doc vêm de [[02 - Fechamento e Cartorio BR]] (números, leis e fontes lá). Regra de ouro do BR: **"concluído" = registrado na matrícula** (CC art. 1.245), não assinado.

## 1. Documentos e due diligence ✍️
> [!todo] ✍️ PRECISA ESCREVER
> - Os checklists por venda/locação/perfil já existem no código — são a lista **canônica e completa**? O que falta?
> - Quais documentos são **obrigatórios para avançar**? (Hoje nada trava o avanço por falta de documento — deveria travar?)
> - Documentos da **empresa vendedora** (CNPJ): quais certidões, quando?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR) [muito é regra legal]:** o que **realmente trava** o fechamento está **na matrícula** — princípio da concentração (Lei 13.097/2015): o comprador de boa-fé só é atingido por ônus averbados na matrícula. O núcleo duro que bloqueia:
> - **Do imóvel:** matrícula atualizada + certidão de ônus reais (penhora/hipoteca/indisponibilidade travam o ato), **IPTU quitado** (dívida é propter rem), débito condominial, habite-se.
> - **Do vendedor PF:** estado civil + anuência do cônjuge (art. 1.647); certidões pessoais (trabalhista/cível/federal/fiscal/protesto) = **prova de boa-fé contra fraude à execução** — importam, mas **não são gate registral** (o CNJ vedou exigir certidões negativas genéricas para registrar).
> - **Do vendedor PJ (CNPJ):** contrato social + comprovação de poderes + Junta Comercial + CNDT + FGTS + fiscais + **certidões dos sócios** (blinda contra desconsideração da PJ, art. 50). Rigor maior — esvaziamento patrimonial é comum.
> **Recomendação para o Cadê:** distinguir no sistema **dois níveis de documento**: (1) **bloqueadores** (matrícula limpa + ITBI pago — sem eles não há registro) → o sistema **deve travar** o avanço; (2) **due diligence de risco** (certidões pessoais) → **não travam**, mas geram um "score de risco" exibido às partes (bom diferencial que não mata conversão). A **matrícula é o dado mais valioso** a extrair/validar. **[MVP]** checklist canônico por perfil + travar nos bloqueadores; automação de OCR/certidões = [Fase 2].
> **Decisão dos sócios / trade-offs:** quão rígido travar. Travar em tudo protege mas gera fricção e abandono; travar só nos bloqueadores legais + sinalizar o resto é o equilíbrio que recomendo. O checklist do código provavelmente precisa **adicionar as certidões de CNPJ e a anuência do cônjuge** — validar com o Luiz.
> **Fontes:** [[02 - Fechamento e Cartorio BR]] §5.

## 2. Contrato e assinatura ✍️
> [!todo] ✍️ PRECISA ESCREVER — decisão jurídica (Luiz)
> - O "aceite auditável interno" (hoje) serve para o go-live, ou precisa de **e-signature legal** (gov.br / ICP-Brasil) antes de contrato vinculante?
> - **Escritura pública** (venda > R$ 45.540) deve **travar** o fechamento até registrar, ou seguir só como aviso (hoje)?
> - Geração do PDF do contrato: modelo/template real (hoje não existe).

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR) — resposta direta às 3 perguntas:**
> 1. **O aceite auditável interno SERVE, sim, para o go-live** — mas só para os atos **pré-cartório** (proposta, reserva, compromisso particular, locação). O STJ (REsp 2.055.717/2025) confirmou que assinatura avançada fora da ICP-Brasil tem "validade jurídica idêntica" à qualificada. Para o aceite do Cadê ser defensável como **avançado** (não só simples), ele precisa de: **hash do documento + carimbo de tempo + autenticação forte (CPF validado + SMS/selfie) + trilha imutável exportável**. Como está (log simples), vincula em baixo risco mas é frágil se impugnado (Tema 1061: o ônus da prova é de quem juntou o documento).
> 2. **Escritura/registro NÃO cabem no app** — exigem **ICP-Brasil qualificada** via e-Notariado/cartório. O correto **não é "travar até registrar" dentro do Cadê**, e sim: o app leva o negócio até o **dossiê pronto pro cartório** e marca "concluído" só quando **o registro na matrícula** é confirmado (CC art. 1.245 — só é dono quem registra). O teto da escritura obrigatória em 2026 é **R$48.630** (30 × SM R$1.621), não R$45.540 — atualizar.
> 3. **Template de contrato:** gerar PDF real a partir de modelo é [MVP] viável e de alto valor (hoje não existe). Assinatura via provedor (ZapSign/Clicksign) com trilha ICP por uso.
> **Recomendação para o Cadê:** **[MVP]** aceite auditável **reforçado** (hash+timestamp+auth forte) para os atos pré-cartório + geração de PDF do contrato + assinatura via provedor. **[Fase 2]** integração com e-Notariado/registro eletrônico (SERP) para orquestrar o fechamento remoto. Não tentar substituir o cartório — entregar o dossiê pronto pra ele.
> **Decisão dos sócios / trade-offs (Luiz):** o nível de assinatura por tipo de ato. Aceite simples é barato e rápido mas frágil em valor alto; integrar ICP/e-Notariado é robusto mas adiciona custo e fricção. Recomendo aceite reforçado (avançado) para tudo pré-cartório e ICP só onde a lei obriga.
> **Fontes:** [[02 - Fechamento e Cartorio BR]] §1, §6, §8.

## 3. Fluxo cartorial (só venda) ✍️
> [!todo] ✍️ PRECISA ESCREVER
> - Quem paga **ITBI, custas e emolumentos** (hoje modelado como do comprador)?
> - **Prestadores cartoriais** (tabelião/despachante): quem aprova, com que critério? É **marketplace** (eles pagam, Cadê fica com %) ou só diretório? As partes escolhem o cartório?
> - O que significa "concluído" (matrícula registrada) e como se confirma.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR) [regra legal] — o código já está certo em partes:**
> - **ITBI/custas: o comprador paga** (padrão legal) — o código está correto. Ordem de grandeza total do fechamento ≈ **3-6% do imóvel** (ITBI 2-3% + escritura ~0,5-1,5% + registro ~0,3-1%). **ITBI é gate**: pago **antes** do registro (cartório exige o comprovante). Base = **valor declarado da transação** (STJ Tema 1113), não valor de referência da prefeitura.
> - **"Concluído" = título REGISTRADO na matrícula** (CC art. 1.245), não a escritura assinada. Confirmação: a certidão/matrícula atualizada mostrando o novo proprietário. O sistema deve marcar "concluído" nesse evento.
> - **Prestadores cartoriais — atenção jurídica importante:** o **cartório NÃO pode pagar comissão a marketplace** (vedada captação de clientela / comissão por indicação — Lei 10.169/2000). Então:
>   - Sobre **tabelião/registrador** → o Cadê só pode ser **diretório/orquestração** (encaminhar ao cartório certo, gerar guias, protocolar via SERP/e-Notariado), monetizado pela facilitação — **nunca** % do emolumento.
>   - Sobre a **camada privada** (despachante, advogado, avaliação, certidões pagas) → **pode ser marketplace com take rate** (eles pagam %). É aqui que a receita cartorial do Cadê é legalmente possível.
>   - **Escolha do cartório:** Tabelião de Notas = escolha livre (dentro da competência); **Registro de Imóveis = SEM escolha** (competência territorial fixa na circunscrição do imóvel). O sistema deve rotear o registro automaticamente pelo endereço do imóvel.
> **Recomendação para o Cadê:** modelar o marketplace de prestadores **só na camada privada** (despachante/advogado aprovados por admin, pagam % à Cadê) e tratar o cartório como **destino roteado, não como fornecedor pagante**. **[MVP]** diretório de despachante + roteamento do registro por endereço; take rate no despachante = [Fase 2] (depende de processar dinheiro).
> **Decisão dos sócios / trade-offs (Luiz):** critério de aprovação dos prestadores privados e se a Cadê quer take rate ou só facilitação. Cobrar % do despachante é legal; do cartório não é — não confundir as duas camadas.
> **Fontes:** [[02 - Fechamento e Cartorio BR]] §2, §3, §7, §8.

## 4. Pagamento / sinal ✍️🆕
> [!todo] 🆕 PRECISA ESCREVER — depende do doc `06 - Planos`
> Hoje "PIX" é só um comprovante enviado entre as partes; **nenhum dinheiro passa pela plataforma**. Definir: a Cadê intermedia sinal/pagamento (gateway/PIX/escrow) ou é sempre off-app? → decide se precisa construir módulo de pagamento.

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado (BR):** o **sinal/arras é contratual e privado** — não há escrow obrigatório por lei. Quem intermedeia dinheiro (QuintoAndar) usa um PSP regulado, não vira banco. **Novidade 2025:** a **conta notarial escrow** (Lei 14.711/2023 + Provimento CNJ 197/2025) formalizou a custódia de sinal via cartório com segregação patrimonial (custo ~0,08% do valor) — é o análogo BR do escrow americano (nos EUA o *earnest money* fica numa title/escrow company neutra, **modelo não transferível** juridicamente).
> **Recomendação para o Cadê:** **[MVP] manter off-app** — o comprovante enviado entre as partes, como já é. Nenhum dinheiro passa pela Cadê no fechamento. É o menor risco e o menor esforço.
> - **[Fase 2+] intermediar o sinal** só se a decisão-âncora de [[06 - Planos, Serviços e Precificação]] for pelo modelo transacional com dinheiro on-app. Aí a opção mais sólida juridicamente para o **sinal de compra** é encostar na **conta notarial escrow do CNJ** (não construir custódia própria, que exige licença de IP). Para aluguel recorrente, o caminho é split via PSP.
> **Fronteira regulatória:** manter saldo de terceiros em nome próprio exige autorização prévia do BC (Res. BCB 80, alterada 09/2025). Não cruzar sem decisão consciente + Luiz.
> **Decisão dos sócios / trade-offs:** off-app perde o float e a "cola" financeira, mas é simples e seguro. On-app abre receitas (garantia, antecipação — caminho da Loft) ao custo de um mini-produto de pagamentos + peso regulatório. Ver análise completa em [[06 - Planos, Serviços e Precificação]].
> **Fontes:** [[00 - Mercado Imobiliario Tech BR-US - Overview]] §3.1-3.4.

## 5. Acompanhamento externo ✍️
> [!todo] ✍️ PRECISA ESCREVER
> Quando as duas partes decidem **seguir sem serviço Cadê**, o negócio vai para "acompanhamento externo". Como esse caso se reconcilia num desfecho (fechou / perdeu)? Que follow-up a Cadê faz (7/30/45 dias)?

> [!tip] 💡 Sugestão do Douglas — pesquisa BR+US, 12/07/2026 — A VALIDAR
> **Prática de mercado:** o "acompanhamento externo" é o reconhecimento honesto de que, como o **registro na matrícula acontece fora do app** (no cartório), a Cadê muitas vezes **não vê o desfecho** automaticamente. Plataformas resolvem isso com **follow-up de confirmação** (cadência de mensagens perguntando "fechou?") + consulta à matrícula.
> **Recomendação para o Cadê:** tratar "acompanhamento externo" como um **estado aberto que precisa ser reconciliado**, não um fim de linha:
> - **Reconciliação automática (ideal, [Fase 2]):** checar periodicamente a **matrícula** do imóvel — se o proprietário mudou, marca **fechou** (mesmo sem serviço Cadê); útil até pra métrica de conversão real.
> - **Reconciliação por follow-up ([MVP]):** cadência **7/30/45 dias** perguntando às partes se o negócio fechou, com botões "fechamos / ainda em andamento / desistimos" que movem o negócio para **concluído** ou **perdido**. Sem resposta em X dias → marcar "perdido (sem confirmação)".
> - O follow-up é o mesmo motor de comunicação do doc [[07 - Comunicação, Suporte e Operação]] (Fase 4) — reusar.
> **Decisão dos sócios / trade-offs:** quanto insistir no follow-up (fricção vs dado). E se vale investir na reconciliação por matrícula (mais preciso, mais esforço técnico — depende de OCR/consulta de matrícula). Recomendo follow-up simples no MVP.
> **Fontes:** [[02 - Fechamento e Cartorio BR]] §3 (registro fora do app) · [[01 - Locacao e Corretor BR-US]] §2.5 (cadências).
