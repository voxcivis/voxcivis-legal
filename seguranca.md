---
layout: default
title: Segurança da Informação
permalink: /seguranca
---

> **⚠️ Documento institucional · Beta fechado.** Versão definitiva publicada após validação por escritório especializado em LGPD/Direito Digital.

---

# Segurança da Informação — VoxCivis

**Versão:** 2.1  
**Vigente desde:** 09/05/2026

## 1. Compromisso institucional

A **SIAS - Soluções em Inteligência Artificial e Sustentabilidade LTDA** opera a plataforma VoxCivis com **segurança e proteção de dados como pilares fundamentais** desde a concepção (*Security by Design*). Adotamos os mais altos padrões de mercado aplicáveis ao nosso estágio atual e evoluímos continuamente nossa postura de segurança conforme o amadurecimento da operação.

## 2. Pilares de segurança em produção

A arquitetura VoxCivis incorpora os seguintes pilares:

### 2.1 Identidade e autenticação
Padrão de mercado **OAuth2 / OpenID Connect** — mesma referência adotada por instituições financeiras e plataformas governamentais. Senhas armazenadas com hash criptográfico. Princípio do menor privilégio em acessos administrativos.

### 2.2 Criptografia em trânsito
**TLS** com renovação automática de certificados em todos os endpoints públicos. Comunicação com fornecedores externos sob HTTPS protegida por acordos contratuais de não-uso para treinamento.

### 2.3 Auditoria completa
Log de operações sensíveis com **retenção de 5 anos**, conforme exigência LGPD. Captura padronizada com rastreabilidade ponta a ponta de cada interação com agentes de IA.

### 2.4 Controle de tráfego
Rate-limiting em múltiplas camadas (por usuário e por IP) protege a plataforma contra abuso, força bruta e exfiltração massiva.

### 2.5 Compliance automatizado: VOX GUARDIÃO
**Diferencial arquitetural** — toda saída de IA passa por gate automatizado que aplica verificação de conformidade (LGPD e Lei 9.504/97) e adiciona **watermark** automático de autoria em 100% das respostas.

### 2.6 Soberania de dados
Infraestrutura hospedada em **território nacional brasileiro**. Dados de clientes residem no Brasil.

## 3. Frameworks de referência adotados

- **LGPD** (Lei 13.709/2018) — base legal da proteção de dados
- **Marco Civil da Internet** (Lei 12.965/2014)
- **OWASP Top 10** — referência para aplicação web segura
- **ISO 27001 / ISO 27701** — referências para gestão de segurança e privacidade
- **NIST Cybersecurity Framework** — referência para postura defensiva

## 4. Resposta a incidentes

Procedimento formal alinhado ao art. 48 da LGPD:

1. Detecção e contenção imediatas
2. Avaliação de severidade pelo DPO
3. **Notificação à ANPD em até 72 horas** quando houver risco aos titulares
4. Comunicação aos titulares afetados em linguagem clara
5. Análise de causa raiz e remediação

**Canal:** <dpo@voxcivis.ai>

## 5. Reporte responsável de vulnerabilidades

Pesquisadores de segurança são bem-vindos. Reporte vulnerabilidades para <dpo@voxcivis.ai> sob disclosure responsável:

- Não exploramos, não retaliamos
- Reconhecemos publicamente colaborações relevantes (com autorização)
- Remediação proporcional à severidade

## 6. Contato

- **DPO:** <dpo@voxcivis.ai>
- **Atendimento geral:** <atendimento@voxcivis.ai>
- **Sede:** SIAS LTDA · Brasília/DF · CNPJ 59.999.302/0001-68

---

*Documento institucional público. Política de Segurança detalhada é documento interno.*
