# LeadBot Checker — Automação de Leads WhatsApp 24h com n8n + IA

> Projeto aberto com ferramentas gratuitas para automatizar qualificação de leads no WhatsApp usando n8n, Gemini e workflows reais. Para pequenos negócios que precisam responder clientes fora do horário sem aumentar custos fixos.

# LeadBot 24h — Atenda clientes no WhatsApp fora do horário e não perca vendas

> Seu cliente chama no WhatsApp às 22h e ninguém responde? Ele vai procurar outro. O LeadBot qualifica leads 24h e entrega oportunidades quentes para você fechar.

**Para quem é:** pequenos negócios, imobiliárias, clínicas, prestadores de serviço e profissionais autônomos que recebem leads pelo WhatsApp e perdem vendas por demora no atendimento.

---


## Problema

Clientes que enviam mensagem no WhatsApp fora do horário comercial têm 3x mais chance de procurar um concorrente. Responder manualmente 24h exige equipe ou ferramentas caras.

## Solução

Workflow n8n + Gemini (IA gratuita) que:
- Recebe mensagens do WhatsApp via webhook
- Classifica a intenção do lead automaticamente
- Responde na hora ou agenda retorno
- Salva o número no Google Sheets para follow-up
- Funciona 24h por dia, 7 dias por semana

## O que você encontra aqui

| Recurso | Descrição |
|---|---|
| [Calculadora de Prejuízo](https://aplanejamento-cloud.github.io/leadbot-checker) | Descubra quanto seu negócio perde quando demora para responder leads |
| [Como qualificar leads no WhatsApp com n8n](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/como-qualificar-leads-whatsapp-n8n.html) | Guia passo a passo do fluxo completo |
| [Automação de leads para pequenos negócios](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/automacao-leads-pequenos-negocios.html) | Estratégias que funcionam sem equipe grande |
| [Chatbot WhatsApp com IA sem custo mensal](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/chatbot-whatsapp-ia-sem-custo-mensal.html) | Comparativa: manual vs. automatizado |
| [Converter leads de madrugada](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/converter-leads-madrugada-whatsapp.html) | Capture e responda fora do horário comercial |
| [Atendimento imobiliário automatizado](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/atendimento-automatico-imobiliaria-n8n.html) | Case prático para imobiliárias |
| [Integração Gemini + n8n grátis](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/gemini-gratis-n8n-automacao.html) | IA sem custo para automação |
| [Recuperar webhook instável](https://aplanejamento-cloud.github.io/leadbot-checkerlearn/webhook-instavel-whatsapp-n8n-recovery.html) | Troubleshooting de automação |

## Stack tecnológica

- [n8n](https://n8n.io) — orquestração de workflows open-source
- Google Gemini — IA gratuita para classificação de intenção
- WhatsApp Business API — via Twilio ou 360dialog
- GitHub Pages — hospedagem do site e conteúdo

## Template gratuito

Download do workflow base n8n (versão Lite): [`leadbot-lite.json`](leadbot-lite.json)

## Observabilidade

- GA4 instrumentado (landing_page_view, cta_click, checkout_start)
- UTM tracking em todos os links de distribuição
- Gumroad sales polling ativo via `/v2/sales`

## Autor

Projeto maintained por [aplanejamento-cloud](https://github.com/aplanejamento-cloud).

---

*Última atualização automática: 2026-08-27T13:53:14Z*


## Como funciona — arquitetura

```
[Visitante chega na landing]
        |
        v
[Landing page — github.io/leadbot-checker]
  - Calculadora: quanto voce esta perdendo com leads nao respondidos?
  - Guias: fluxos prontos para n8n + WhatsApp + Gemini
        |
        v
[Visitante clica no CTA "Quero LeadBot 24h"]
        |
        v
[Redirector Worker — Cloudflare]
  - Captura: slug, UTMs, timestamp, path
  - Registra em R2 (sale-ledger/click/<uuid>.json)
  - NAO altera destino, NAO adiciona parametros
        |
        v
[Gumroad — planificador7.gumroad.com/l/leadbot-24h]
  - Checkout Gumroad (pagamento/entrega)
  - Produto: setup n8n leadbot-lite (sem IA, 2 nodes)
```

## Stack

| Camada | Tecnologia | Funcao |
|--------|-----------|--------|
| Automacao | n8n | Orquestracao do fluxo de qualificacao |
| IA | Google Gemini (free tier) | Classificacao de intencao do lead |
| Canal | WhatsApp API (Twilio) | Envio e recebimento de mensagens |
| Hospedagem | Cloudflare Workers | Redirector com logging de cliques |
| Storage | Cloudflare R2 | Ledger de clicks (sale-ledger bucket) |
| Analytics | GA4 | landing_page_view, cta_click, checkout_start |
| Frontend | HTML/CSS vanilla | Landing + 14 learn pages (GitHub Pages) |

## Workflow do leadbot-lite (exemplo)

O template leadbot-lite.json (2 nos n8n) demonstra o fluxo minimo:

1. **Webhook recebe mensagem** — entrada via Twilio WhatsApp
2. **Regra de qualificacao** — classifica como QUENTE/MORNO/FRIO
3. **Follow-up automatico** — mensagens fora do horario comercial

> leadbot-lite e SEM IA generativa. Usa regras. O plano com Gemini (IA) esta documentado em: chatbot-whatsapp-ia-sem-custo-mensal.html

## Fluxo tipico — passo a passo

1. Cliente envia "oi" ou "quero orcamento" no WhatsApp
2. Twilio entrega para webhook do n8n (n8n cloud ou self-hosted)
3. n8n aplica regras: horario saudacao / fora-horario captura
4. Lead qualificado recebe follow-up automático
5. CRM ou painel recebe lead quente para fechamento humano

## Guias e recursos

| Recurso | Descricao |
|---------|-----------|
| [Qualificar leads WhatsApp com n8n](https://aplanejamento-cloud.github.io/leadbot-checker/learn/como-qualificar-leads-whatsapp-n8n.html) | Fluxo passo a passo |
| [Automacao para pequenos negocios](https://aplanejamento-cloud.github.io/leadbot-checker/learn/automacao-leads-pequenos-negocios.html) | Caso de uso SME |
| [Chatbot WhatsApp IA sem custo](https://aplanejamento-cloud.github.io/leadbot-checker/learn/chatbot-whatsapp-ia-sem-custo-mensal.html) | Gemini + n8n |
| [Converter leads de madrugada](https://aplanejamento-cloud.github.io/leadbot-checker/learn/converter-leads-madrugada-whatsapp.html) | Resposta fora horario |
| [Webhook instavel recovery](https://aplanejamento-cloud.github.io/leadbot-checker/learn/webhook-instavel-whatsapp-n8n-recovery.html) | Tratamento de falhas |
| [Calculadora de prejuizo](https://aplanejamento-cloud.github.io/leadbot-checker) | Quanto voce esta perdendo? |

## Casos de uso

- Pequena imobiliaria: atendimento automatico fora de horario
- Clinica/estetica: qualificacao antes da consulta
- E-commerce: captura e resposta 24h sem custo fixo adicional
- Prestador de servico: follow-up pos-orcamento automatico

## Saiba mais

- [Todos os guias](https://aplanejamento-cloud.github.io/leadbot-checker) — landing completa
- [Template n8n leadbot-lite](https://leadbot-redirector.aplanejamento.workers.dev/r/leadbot-lite?utm_source=github&utm_medium=readme-business&utm_campaign=leadbot24h&utm_content=readme-cta-b109) — download via Gumroad
- [n8n workflow JSON import](https://aplanejamento-cloud.github.io/leadbot-checker/learn/workflow-n8n-importar-json.html) — importar workflows prontos
- [Gemini gratis + n8n](https://aplanejamento-cloud.github.io/leadbot-checker/learn/gemini-gratis-n8n-automacao.html) — IA sem custo mensal

## Contribuindo

Pull requests sao bem-vindos. Issues com bugs ou duvidas sobre n8n tambem.

## Licenca

MIT — uso livre para projetos comerciais ou pessoais.
