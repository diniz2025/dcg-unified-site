# DCG Unified Site — Repositório oficial

Plataforma digital da **DCG Corretora de Seguros LTDA** (28 anos · CNPJ 16.383.565/0001-35 · SUSEP 10.2010993.8).

Corredor institucional: **SinHoRes Osasco Alphaville · FHORESP · IVI · AETERNUM**.

## Filosofia

> "Simplificar. Integrar. Automatizar. Vender. Proteger. Escalar."

Três influências:
- **Steve Jobs** — sofisticação = simplicidade
- **Alan Turing** — lógica antes da estética
- **Linus Torvalds** — engenharia robusta acima de vitrine

3 perguntas-filtro antes de criar qualquer coisa:
1. Aumenta vendas?
2. Reduz risco/trabalho?
3. Cria ativo para a DCG?

## Stack

```
Frontend    Lovable (React + Tailwind + Vite)
Design      Tailwind tokens (Fraunces + Inter + JetBrains Mono)
Backend     Supabase (Auth + Postgres + RAG p/ Tim)
AI          Claude Opus · Manus AI · GitHub Copilot · MFA agents
Hosting     VPS Hostinger · nginx · Let's Encrypt
Repo        GitHub diniz2025/dcg-unified-site
Protocolo   Canal-Ação-Tim · LGPD end-to-end · SUSEP/ANS compliance
```

## Estrutura do repositório

```
dcg-unified-site/
├── README.md
├── LICENSE (MIT)
├── docs/
│   ├── BLUEPRINT.md          → visão 360° do site (9 páginas, 6 trilhas)
│   └── design-tokens.json    → design system Lovable-ready
├── examples/                 → protótipos HTML estáticos (referência visual)
│   ├── home-prototype.html   → hero + ticker + trilhas + cases reais
│   └── sinhores.html         → trilha dedicada SinHoRes × DCG
└── src/                      → código Lovable (React + Tailwind) — WIP
```

## Personas-alvo

| Persona | Volume | Trilha preferida |
|---------|--------|-------------------|
| Hotel/restaurante SinHoRes Osasco | alto | `/sinhores` |
| Empresa 10-100 vidas | alto | `/empresas` |
| Corretor autônomo parceiro | médio | `/corretores` |
| Indústria 100-500 vidas | médio | `/empresas` (TCO estimator) |
| Tomador decisão risco psicossocial | médio | `/nr1` (NR-1 + IVI) |
| Membro FHORESP | institucional | `/sinhores` + `/nr1` (15% off) |

## Governança

- **Nunca** afirmar funcionamento sem evidência (Protocolo de Confiança DCG)
- **Nunca** inventar lei, norma, preço, cobertura ou operadora
- **Nunca** publicar credenciais em código público
- **Sempre** LGPD desde a arquitetura (RIPD, base legal, retenção)
- **Sempre** manter rastro de mudanças em commit

## Tim — assistente IA

A DCG opera com **Tim**, seu segundo cérebro estratégico. Tim:
- Auxilia corretores em cotações rápidas (5 perguntas, 48h SLA)
- Mantém ticker regulatório atualizado (ANS, SUSEP, STF, MTE, ANPD)
- Documenta decisões regulatórias em BLUEPRINT

## URL do produto

Repo: https://github.com/diniz2025/dcg-unified-site  
Site alvo: https://www.dcgseguros.com.br (atualmente placeholder Hostinger)

## Convenções de commit

```
feat(seo): adicionar schema.org local business
fix(login): corrigir redirect pós-auth
docs(blueprint): atualizar decisões aprovadas
chore(tokens): v3 — adicionar coral light
```

## Contato direto

- **Comercial:** comercial@dcgseguros.com.br
- **Diniz:** diniz@dcgseguros.com.br
- **WhatsApp DCG:** (11) 93075-9163
- **Slack workspace:** dcg corretora de seguros ltda
- **Calendly:** calendly.com/dcgseguros

---

*Construído por Tim + Diniz. Lovable → GitHub → VPS Hostinger. Última revisão 2026-09-21.*
