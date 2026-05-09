---
layout: default
title: Segurança da Informação
permalink: /seguranca
---

> **⚠️ Documento em fase final de revisão · resumo público.** A Política de Segurança completa é documento interno da SIAS LTDA. Esta página é um resumo das medidas implementadas, com foco em transparência ao usuário.

---

# Segurança da Informação — VoxCivis

**Última atualização:** 08/05/2026

## 1. Compromissos da SIAS LTDA

A SIAS adota controles de segurança alinhados às melhores práticas de mercado e à conformidade com a LGPD (Lei 13.709/2018).

## 2. Autenticação e controle de acesso

- **OAuth2 / OIDC** via Keycloak (padrão usado por instituições financeiras)
- **Senhas armazenadas com hash** criptográfico (nunca em texto)
- **JWT de sessão de curta duração** (15 minutos · refresh automático)
- **MFA (autenticação multifator)** disponível para planos Completo e Sob Medida
- **Login social** via Google · Microsoft (OAuth2 padrão)

## 3. Criptografia

- **Em trânsito:** TLS 1.3 (HTTPS automático via Let's Encrypt)
- **Em repouso:** dados criptografados no banco PostgreSQL
- **Backups criptografados** com chave separada

## 4. Auditoria e monitoramento

- **Audit log** de todas operações sensíveis · retenção mínima de **5 anos** (defesa em fiscalização ANPD)
- **Rate-limit** em 3 camadas (segundo · minuto · dia) + por IP
- **Detecção de anomalias** automatizada
- **Alertas em tempo real** para a equipe técnica

## 5. Gate de compliance (VOX GUARDIÃO)

Toda saída dos agentes de IA passa pelo VOX GUARDIÃO — gate automatizado que:

- Detecta conteúdo potencialmente eleitoral (Lei 9.504/97)
- Detecta dados pessoais em outputs (LGPD)
- Aplica watermark de autoria em todas as respostas
- Sistema de 4 cores: VERDE (libera) · AMARELO (ajusta) · LARANJA (revisa) · VERMELHO (bloqueia)

## 6. Infraestrutura

- **Hospedagem:** Hostinger (Brasil) com containers Docker isolados
- **Banco de dados:** PostgreSQL com Row-Level Security (RLS)
- **Cache:** Redis (rate-limit + JWKS)
- **Storage:** MinIO (S3-compatible) self-hosted
- **TLS automático:** Traefik com Let's Encrypt

## 7. Resposta a incidentes

Em caso de incidente de segurança:

1. Equipe técnica é alertada automaticamente
2. DPO avalia e classifica severidade
3. Notificação à ANPD em até **72 horas** (se aplicável · LGPD art. 48)
4. Comunicação aos titulares afetados (se aplicável)
5. Análise de causa raiz e remediação documentada
6. Histórico mantido em audit log por 5 anos

## 8. Vulnerabilidades

Ao identificar uma vulnerabilidade, **reporte responsavelmente** para <dpo@voxcivis.ai>. Não exploraremos, não retaliaremos e agradecemos a colaboração.

## 9. Conformidade

- **LGPD** (Lei 13.709/2018)
- **Marco Civil da Internet** (Lei 12.965/2014)
- **ISO 27001/27701** (boas práticas, em processo de avaliação)
- **OWASP Top 10** (aplicação web)

## 10. Contato

- **DPO:** <dpo@voxcivis.ai>
- **Suporte:** <contato@voxcivis.ai>

---

*Documento de referência pública. Política de Segurança completa é interna.*
