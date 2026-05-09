---
layout: default
title: Segurança da Informação
permalink: /seguranca
---

> **⚠️ Documento institucional · Beta fechado.** Esta página apresenta os pilares de segurança da arquitetura VoxCivis em produção. A Política de Segurança completa é documento interno da SIAS LTDA. Versão definitiva publicada após validação por escritório especializado em LGPD/Direito Digital.

---

# Segurança da Informação — VoxCivis

**Última atualização:** 09/05/2026  
**Versão:** 2.0 · alinhada com arquitetura V3.9 em produção

## 1. Compromisso institucional

A **SIAS - Soluções em Inteligência Artificial e Sustentabilidade LTDA** opera a plataforma VoxCivis com **segurança e proteção de dados como pilares fundamentais** desde a concepção (*Security by Design*). Adotamos os mais altos padrões de mercado **aplicáveis ao estágio atual** da operação, com plano formal de evolução à medida que crescemos.

Esta página declara, com transparência integral, **o que está implementado** em produção e **o que está planejado** para evolução. Sem ambiguidade.

## 2. Pilares em produção (arquitetura V3.9)

### 2.1 Identidade e autenticação
Padrão de mercado **OAuth2 / OpenID Connect** — mesmo adotado por instituições financeiras.

- **Keycloak** auto-hospedado · realm dedicado `voxcivis` · JWT issuer
- Validação de tokens via cache JWKS em Redis
- Hash criptográfico de senhas (Keycloak)
- Princípio do menor privilégio em acessos administrativos

### 2.2 Criptografia em trânsito
- **TLS** automático via Traefik com Let's Encrypt
- Domínios: `api.voxcivis.ai` · `auth.voxcivis.ai` · `legal.voxcivis.ai`
- Comunicação com LLMs externos via HTTPS sob DPA de não-treinamento

### 2.3 Auditoria completa
- **Audit log** em PostgreSQL com retenção LGPD de **5 anos**
- Captura via `AuditMiddleware` em modo *fire-and-forget* (zero impacto em latência)
- Estrutura padronizada · rastreabilidade ponta-a-ponta de cada interação com IA

### 2.4 Controle de tráfego (rate-limit)
- 3 camadas temporais: segundo · minuto · dia
- Aplicação dual: por usuário (JWT) + por IP
- Contadores em Redis · resposta `429 Too Many Requests`

### 2.5 Compliance automatizado: VOX GUARDIÃO
**Diferencial arquitetural** — toda saída de IA passa por gate automatizado:

- Workflow dedicado em n8n (WF-02) · 100% das respostas
- **Watermark automático** em toda resposta aprovada
- **Bloqueio ativo** de conteúdo potencialmente eleitoral (Lei 9.504/97)
- Decisões registradas no audit log

### 2.6 Infraestrutura
- **Hospedagem em território nacional:** Hostinger Brasil · servidor dedicado
- Orquestração via Easypanel · rede Docker isolada (`easypanel-vox_civis`)
- Containers: Traefik · Keycloak · FastAPI · PostgreSQL · Redis · n8n · OpenWebUI
- **Soberania de dados:** dados de clientes residem em território brasileiro

### 2.7 Pipeline da requisição (defense in depth)
Princípio **fail-fast** — toda validação ocorre antes da chamada ao LLM:

```
Cliente → Traefik (TLS) → CORS → Auth (JWKS) → Rate-limit (Redis) →
Audit (Postgres) → Roteamento → Agente (n8n WF-01) → LLM →
GUARDIÃO (n8n WF-02) → Watermark → Cliente
```

## 3. Frameworks e referências adotados

A arquitetura VoxCivis tem como referência os principais frameworks consolidados de mercado, aplicados na medida adequada ao estágio atual:

- **LGPD** (Lei 13.709/2018) — conformidade implementada
- **Marco Civil da Internet** (Lei 12.965/2014) — conformidade implementada
- **OWASP Top 10** — referência aplicada no design da aplicação
- **ISO 27001 / ISO 27701** — norte arquitetural · certificação no plano de evolução
- **NIST Cybersecurity Framework** — referência para postura defensiva

## 4. Plano de Evolução Contínua

Os controles abaixo **não estão implementados no MVP** e seguem cronograma formal de implementação proporcional ao crescimento da operação:

**Horizonte 1 (até Q3/2026)**
- MFA por plano · Login social Google/Microsoft
- Criptografia em repouso · Backups com chave separada
- Row-Level Security (RLS) no PostgreSQL · MinIO para objetos
- Alertas em tempo real

**Horizonte 2 (12-18 meses)**
- HSM/KMS · WAF dedicado · SIEM · Detecção de anomalias · Pen test anual

**Horizonte 3 (12-24 meses)**
- ISMS formal · Comitê de Segurança · Certificações ISO 27001/27701 e SOC 2

## 5. Resposta a incidentes

Procedimento alinhado ao art. 48 da LGPD:

1. Detecção e contenção via monitoramento da arquitetura
2. Avaliação de severidade pelo DPO
3. **Notificação à ANPD em até 72 horas** quando houver risco aos titulares
4. Comunicação aos titulares afetados em linguagem clara
5. Causa raiz documentada no audit log (5 anos)

**Canal:** <dpo@voxcivis.ai>

## 6. Reporte responsável de vulnerabilidades

Pesquisadores de segurança são bem-vindos. Reporte sob *disclosure responsável* para <dpo@voxcivis.ai>:

- Não exploramos, não retaliamos
- Reconhecemos publicamente colaborações relevantes (com autorização)
- Remediação proporcional à severidade

## 7. Contato

- **DPO:** <dpo@voxcivis.ai>
- **Atendimento geral:** <atendimento@voxcivis.ai>
- **Sede:** SIAS LTDA · Brasília/DF · CNPJ 59.999.302/0001-68

---

*Documento de referência pública alinhado com a arquitetura V3.9 em produção. Política de Segurança completa é interna.*
