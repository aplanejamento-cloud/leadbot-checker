# LeadBot Checker — Automação de Leads WhatsApp 24h com n8n + IA

> Projeto aberto com ferramentas gratuitas para automatizar qualificação de leads no WhatsApp usando n8n, Gemini e workflows reais. Para pequenos negócios que precisam responder clientes fora do horário sem aumentar custos fixos.

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
