# BLUEPRINT — DCG Unificada

**Domínio único proposto:** `www.dcgseguros.com.br`
**Subdomínios atuais (mantidos, mas redirecionados):**
- `crmdcg.com` → CRM operacional (link direto /app)
- `dcgseguros.io` → Corretores Pro (link direto /corretores)
- `dcgnr1ivi.com` → NR-1 + IVI (link direto /nr1)
- `prospector.dcgseguros.io` → DCG Data Intelligence (link direto /data)
- `faro.dcgseguros.io` → Farol IA (link direto /faro)

## Filosofia

**Steve Jobs · simplicidade é a sofisticação suprema.**
**Alan Turing · lógica acima de estética vazia.**
**Linus Torvalds · engenharia robusta > vitrine decorativa.**

Um site. Uma marca. Cinco produtos. Cada um com profundidade própria, **sem que o visitante se perca**.

## Design system

- **Tipografia display:** Fraunces (serif, autoridade) — títulos H1/H2
- **Tipografia corpo:** Inter (sans, legibilidade) — parágrafos, navegação
- **Tipografia mono:** JetBrains Mono — dashboards, números, calculadoras, tickers
- **Paleta:**
  - Navy profundo `#0A1F44` — texto principal, hero
  - Pearl `#F8F7F4` — fundos claros
  - Gold `#C8A85D` — destaques, CTAs premium
  - Slate `#5A6B82` — textos secundários
  - Coral `#E2725B` — alertas regulatórios
- **Movimento:** scroll suave, parallax sutil, micro-interações (hover, transições 200ms)
- **Responsivo:** mobile-first, breakpoints em 480 / 768 / 1024 / 1440
- **Acessibilidade:** AA mínimo, contraste verificado

## Estrutura de informação (1 página + sub-rotas)

### `/` — Home (a entrada)
1. **Hero** — manifesto 1-linha, manifesto 3-linhas abaixo
   - "28 anos protegendo empresas brasileiras"
   - Botão primário: "Fale com Tim, seu consultor IA" (tim@dcgseguros.com.br ou chat)
   - Botão secundário: "Diagnóstico 60 segundos" (inicia quiz)
2. **Trust strip horizontal** — ANS · SUSEP · LGPD · CNPJ 16.383.565/0001-35 · SUSEP 10.2010993.8
3. **Números DCG** — 28 anos · 12.000+ empresas atendidas · 38M+ empresas mapeadas (data lake) · 6.000+ vidas em planos · 99% retenção
4. **5 trilhas de produtos** (cards grandes horizontais, com prévia visual)
5. **Regulatório em destaque** — Portaria 1.419/2024, ADPF 1316, Resolução CNSP 493/2026 — selos clicáveis
6. **Casos reais** (3 cards antigos do dcgseguros.io)
7. **Manifesto filosófico** — Steve Jobs · Alan Turing · Linus Torvalds (3 parágrafos curtos)
8. **CTA final** — "Converse com Tim" / "Agende com Diniz"
9. **Footer** — todas as áreas, contato, CNPJ, SUSEP, mapa do site, blog, política privacidade

### `/diagnostico` — Quiz IA interativo (Lovable)
8 perguntas → classifica empresa entre 4 trilhas (Saúde · Property · Vida · Responsabilidade) → gera **recomendação personalizada Tim** + lead captura → CRM interno
- Single source of truth para "entrada do funil"
- Pode virar demo do "Tim" (assistente IA) com Natural Language input

### `/empresas` — DCG institucional
História, números, certificações, equipe, filosofia, casos de sucesso
Sub-páginas: `/empresas/cases`, `/empresas/equipe`, `/empresas/politica-lgpd`

### `/corretores` — DCG Corretores Pro (antigo dcgseguros.io)
3 planos (Starter/Pro/Premium) detalhados. CTA trial 7 dias.
Inclui:
- Tabela de comparação interativa
- Calculadora "quanto vou economizar?" (estimativa mensal)
- Mapa de cobertura (38M+ empresas)
- Logos de operadoras parceiras
- Depoimentos
- Blog embutido: 5 posts selecionados

### `/data` — DCG Data Intelligence (Prospector/Faro)
Prospecção B2B. 38M+ empresas. IA abordagem comercial. CNAE filters. LGPD compliance.
- Demo embutida: filtrar por CNAE + UF + porte → lista de até 10 empresas exemplo (mock)
- Tabela de preços de uso da plataforma
- Enfatizar: B2B, compliance legítimo, dados públicos Receita Federal

### `/nr1` — DCG + IVI (antigo dcgnr1ivi.com)
Tudo sobre NR-1, GRO/PGR, riscos psicossociais.
- Quiz/Diagnóstico IVI (já existe, embed)
- Tabela de preços por nº funcionários (com desconto FHORESP)
- Carta regulatória completa:
  - Portaria MTE 1.419/2024 (cap 1.5 - psicossociais)
  - Vigência 26/05/2026
  - ADPF 1316 STF (suspensão 90 dias)
  - Próximas etapas regulatórias
- Materiais engajamento mensal (downloads)

### `/crm` — CRM interno (crmdcg embed ou redirect)
Login Lovable autenticado. Página de pré-login com screenshot mock + vídeo curto.

### `/blog` — Inteligência DCG
Timeline editorial regulatória + cases + cultura DCG.

### `/contato` — Conversar com Tim
Form inteligente multi-categoria:
- Sou empresa (consultivo)
- Sou corretor (trial Corretores Pro)
- Sou profissional SST (NR-1)
- Sou desenvolvedor (API)
- Imprensa/parceiros

### `/playbook` — Manifesto filosófico (jobs/turing/torvalds)

## Surpresas técnicas (que diferenciam de qualquer concorrente)

### 1. **Tim — Assistente IA na barra flutuante**
Botão flutuante canto inferior direito. Chat que:
- Lê contexto: "Sou restaurante em Osasco com 25 funcionários"
- Responde: "Para esse perfil, recomendo começar pela nossa trilha NR-1 (Cap. 1.5) + Plano de saúde empresarial Amil/SulAmérica. Como é FHORESP, você tem 15% de desconto no NR-1. Posso abrir o quiz?"
- Memória de sessão (cookie)
- Encaminha para humano (Diniz) se pedir "falar com pessoa"
- API: OpenAI-compatible (gemini-2.5-pro ou minimax-2p7)
- Logs: Supabase com isolamento

### 2. **Calculadora FAP em tempo real**
Widget com 3 inputs: CNAE (select), Nº acidentes últimos 24 meses, Estado (UF).
Calcula economias potenciais em FGTS/INSS com novo FAP.
Mostra também em "cenário pior" / "cenário otimizado".

### 3. **Live Regulatory Ticker**
Barra superior animada com:
- "ANS publicou: nova faixa etária #7"
- "SUSEP CNSP 493/2026: novos produtos"
- "STF ADPF 1316: 90 dias para adequação psicossocial"
Auto-alimenta via API ANS + SUSEP (crawler 4x/dia).

### 4. **Compliance Score por serviço**
Cada serviço carrega badges certificadas:
- "Saúde empresarial · LGPD ✓ ANS ✓"
- "NR-1 com IVI · MTE 1.419/2024 ✓ STF ADPF 1316 ✓"
- "Data Intelligence · Receita Federal pública ✓ LGPD Art. 7º ✓"

### 5. **Comparador visual de planos em TCO**
Comparativo.dcgseguros.com.br (que está desativado) pode voltar como **TCO estimator**:
- Inputs: nº funcionários, perfil etário médio, UF, plano atual
- Output: economia anual estimada com migração Amil/SulAmérica

### 6. **Mapa do Brasil interativo**
Visualização 38M+ empresas via Prospector (DEMO público):
- Hover estado: "SP: 8.2M empresas, 14% com plano empresarial"
- Click: drill-down por CNAE

### 7. **Linha do tempo regulatória**
Página dedicada `/regulatorio` mostrando evolução:
- 2019 LGPD
- 2023 SUSEP resolução
- 2024 Lei 15.040/24 (saúde suplementar)
- 2024 MTE 1.419/2024
- 2025 NR-1 ampliada
- 2026 ANS reajustes
- 2026 STF ADPF 1316
- 2026 Resolução CNSP 493/2026
Marcos grandes, com aplicação prática DCG para cada um.

### 8. **Suspeito Patterns: Health Score da empresa**
Possível widget futuro: dado CNPJ, score "saúde corporativa" (mock; precisa decisão LGPD).

## Plataforma técnica (per DCG.stack)

| Camada | Tecnologia | Responsabilidade |
|--------|-----------|-----------------|
| Front | Lovable / Next.js | UI reativa |
| Auth | Supabase | Login, sessão, RLS |
| DB | Supabase PostgreSQL | Leads, blog, configurações |
| Edge | Cloudflare | CDN, WAF, SSL |
| Hosting produção | VPS Hostinger | domínios e emails |
| CRM | crmdcg (manter) | leads operacionais |
| Email | Postfix + OpenDKIM | outbound |
| WhatsApp | Z-API | chat + alertas |
| Analytics | Plausible (LGPD) | pageviews |
| Forms | Tally | conversões |
| Ticker Regulatory | Cron + gsk crawler | auto-feed |
| AI Tim | gsk via VPS | NLP |
| Mapa Brasil | SVG estático | visual |

## Redirects 301 (preservar SEO)

```
crmdcg.com/* → www.dcgseguros.com.br/crm
dcgseguros.io/* → www.dcgseguros.com.br/corretores
dcgnr1ivi.com/* → www.dcgseguros.com.br/nr1
prospector.dcgseguros.io/* → www.dcgseguros.com.br/data
faro.dcgseguros.io/* → www.dcgseguros.com.br/faro
comparativo.dcgseguros.com.br/* → www.dcgseguros.com.br/comparar (renascer aqui)
hub.dcgseguros.com.br/* → www.dcgseguros.com.br/playbook ou /blog
```

## Próximos passos

1. **AGORA**: apresentar blueprint ✅
2. Criar design tokens (`/projects/dcg-unified-site/design-tokens.json`) — Lovable-friendly
3. Gerar amanhã com Lovable: hero + 5 trilhas + footer
4. Iterar: quiz, calculadora, ticker
5. Deploy: VPS Hostinger + Cloudflare
6. Configurar 301 dos antigos
7. Indexação: sitemap, search console
8. Tracking: Plausible + Search Console

## Decisões pendentes (precisam de input do Diniz)

| # | Decisão | Opções | Recomendação |
|---|---------|--------|--------------|
| 1 | Domínio raiz | `www.dcgseguros.com.br` (atual, vazio) vs novo | **Atual** · autoridade |
| 2 | 28 anos | Corrigir de "27" para "28" (aniversário) | **28** · aniversário recente |
| 3 | Tom "Tim" no chat | Consultivo DCG (não jargão tech) | Sim |
| 4 | Logos operadoras na home | só `/corretores` ou home também | só `/corretores` |
| 5 | Mostrar ADPF 1316 | Sim, com disclaimer jurídico | Sim, com nota |
| 6 | Conteúdo de cultura na home | jobs/turing/torvalds | sim, curto |
| 7 | Saúde pública | Tudo SUSEP/LGPD correto, sem prometer cobertura | logo abaixo |
| 8 | Quem mantém subdomínios? | Lovable standalone ou embed? | **embed simples** |

## ✅ DECISÕES APROVADAS PELO DINIZ (2026-09-21 05:47)

1. **Sim** — incluir SinHoRes Osasco Alphaville em destaque na home + trilha dedicada em `/sinhores`
2. **Sim** — incorporar referências reais a IVI, FHORESP e AETERNUM
3. **Dr. Edson** = Presidente do SinHoRes Osasco Alphaville + Diretor Executivo da FHORESP
4. **Sim** — posso renomear pasta `DCG Wingman Backup` no Drive → `Tim Backups` (executado, status 200)

## Mudanças aplicadas no protótipo (versão 2)

- Hero: passou a destacar Dr. Edson com autoridade institucional (avatar/badge, texto curto)
- Trust strip de 12 operadoras reais adicionada (dedicada)
- Trilhas passaram de 5 para 6:
  - **SinHoRes Osasco** (featured com escala 1.02 e borda gold)
  - Empresas
  - Corretores Pro
  - Data Intelligence (Prospector DCG)
  - NR-1 + IVI
  - **AETERNUM** (nova trilha — parceria estratégica)
- Seção "Cases Reais" com 6 cards identificados nominalmente + CNPJ quando aplicável
- Footer com parceiros institucionais explícitos (SinHoRes · FHORESP · IVI · AETERNUM · HOC)
- Voice de Tim: prompt actualizado para falar "corredor institucional FHORESP" quando cliente fala em SinHoRes/FHORESP

## Operadoras parceiras (texto home)

12 logos-tier-1: Amil · Bradesco Saúde · SulAmérica · Porto Saúde · Hapvida · MedSenior · NotreDame · Alice · Sompo · Care Plus · Omint · Tokio Marine

## Voz institucional / co-brand

Além de DCG + IVI (já tinha), o site passa a mencionar como co-brand ativo:
- DCG × IVI (NR-1 + telepsicologia — vendido como jornada completa)
- DCG × SinHoRes Osasco Alphaville (trilha premium para associados)
- DCG × FHORESP (desconto NR-1 institucional via Dr. Edson)
- DCG × AETERNUM (programa performance humana executiva)

## Métricas de sucesso (90 dias)

- Pages únicas indexadas: 50+ (SEO)
- Sessões orgânicas/mês: 5.000+
- Leads qualificados/mês: 200+ (CRM)
- Conversão diagnóstico→agendamento: 8%+
- Tempo médio na home: 4min+
- Bounce: <55%
- LCP home: <2.5s
- Core Web Vitals: 90+ Lighthouse
