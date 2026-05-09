---
layout: default
title: Política de Privacidade
permalink: /privacidade
---

> **⚠️ Documento em fase final de revisão jurídica · Beta fechado.** Versão definitiva publicada após validação por escritório especializado em LGPD/Direito Digital. Prazo previsto: 18/05/2026. Para dúvidas: <dpo@voxcivis.ai>.

---


# Política de Privacidade — Vox Civis

**Versão:** 1.6  
**Data de Vigência:** 18 de maio de 2026  
**Última Atualização:** 9 de maio de 2026

---

## Changelog

| Versão | Data | Alterações |
|--------|------|-----------|
| 1.6 | 09/05/2026 | Seção 9 reescrita com tom executivo e honestidade integral: (1) abertura institucional posicionando segurança como pilar arquitetural; (2) controles em produção apresentados em 8 pilares (A-H) com contexto de mercado; (3) frameworks (LGPD, OWASP, ISO 27001/27701, NIST) declarados como REFERÊNCIAS adotadas no design (não como certificações obtidas); (4) Plano de Evolução Contínua organizado em 3 horizontes temporais (Q3/2026, 12-18m, 12-24m); (5) novas seções 9.4 (Resposta a Incidentes) e 9.5 (Disclosure Responsável) |
| 1.5 | 09/05/2026 | (1) Seção 9 reescrita 100% baseada na arquitetura V3.9 efetivamente em produção (fontes: 3 diagramas Visão Geral · Ciclo de Request · Topologia); (2) Removidas das declarações atuais e movidas para Roadmap (Seção 9.2): MFA por plano, login social Google/Microsoft, criptografia em repouso, backups criptografados, Row-Level Security (RLS), MinIO, alertas em tempo real, detecção de anomalias; (3) JWT "15 minutos" substituído por declaração genérica (cache JWKS confirmado em fotos, TTL específico não); (4) Seção 11.5 lista de auto-hospedados removeu MinIO (não confirmado nas fotos da V3.9) |
| 1.4 | 09/05/2026 | (1) Seção 5.1 substitui exemplos genéricos (AWS, Auth0, etc.) pelos operadores reais (Hostinger, Keycloak, Anthropic, OpenAI, Asaas, Plausible, Sentry); (2) Seção 9 reescrita: separa controles efetivamente implementados de roadmap declarado; remove afirmações sobre HSM/KMS/WAF/Zero Trust/criptografia E2E que não correspondem ao estado atual; (3) Seção 11.4 marcada como roadmap técnico; (4) Seção 13: nome do DPO preenchido (Francisco de Assis Ferreira Braga Filho); telefone e endereço removidos (e-mail é canal único); (5) Seção 7.8: portal fantasma substituído por canal real de exercício de direitos via e-mail; (6) numeração de seções corrigida (13/14/15/16); (7) typo "Voz Civis" corrigido; (8) Lei 8.884/94 substituída por art. 195 CTN |
| 1.3 | 08/05/2026 | (1) Seção 11.0 item 5 prevê evolução do produto com novos agentes especializados e produtos premium, mantendo o consentimento existente válido para inclusões equivalentes em natureza e finalidade; (2) checkbox 3.1.B reescrito de forma extensível ("agentes especializados e funcionalidades da plataforma") sem listar nomes específicos sujeitos a expansão futura |
| 1.2 | 08/05/2026 | (1) Seção 11.0 estabelece modelo de consentimento opt-in granular com ativação futura para uso de dados anonimizados em refinamento dos agentes; (2) Seção 11.5 nomeia explicitamente fornecedores externos de IA (Anthropic e OpenAI) e formaliza política de não-uso de dados para treinamento; (3) distinção entre componentes auto-hospedados (OpenWebUI, Keycloak, PostgreSQL, Redis, MinIO, N8N) e fornecedores externos com transferência internacional; (4) checkbox de cadastro (3.1.B) reescrito com finalidade específica e tempo de ativação claro |
| 1.1 | 17/04/2026 | Melhorias cirúrgicas de conformidade identificadas em auditoria: (1) Captura prática de consentimento com banner granular, checkbox isolado, centro de preferências e registro imutável; (2) Formatos de resposta para direitos LGPD (JSON/CSV/PDF) + portal de autoatendimento; (3) Notificação proativa à ANPD em 72h + registro de todos incidentes; (4) Auditoria de terceiros com DPA obrigatório; (5) Privacy by Design e Privacy by Default conforme Art. 46 §2º LGPD; (6) Contextualização para Vox Civis com 5 agentes de IA isolados, VOX GUARDIÃO como camada de compliance, metadados de uso criptografados |
| 1.0 | 17/04/2026 | Versão inicial — Lançamento do documento de conformidade LGPD |

---

## 1. Introdução

A **SIAS - Soluções em Inteligência Artificial e Sustentabilidade LTDA** ("**a Vox Civis**", "**nós**", "**a Empresa**") é uma plataforma SaaS de inteligência territorial com Inteligência Artificial que fornece análise de dados geoespaciais, comportamentais e sociodemográficos abrangendo todos os 5.571 municípios brasileiros.

A Vox Civis opera através de **5 agentes de IA especializados** com isolamento por funcionalidade:
- **VOX RADAR:** Monitoramento de tendências territoriais e de mercado
- **VOX PULSO:** Análise de saúde, bem-estar e indicadores municipais
- **VOX CONEXÃO:** Mapeamento de relacionamentos, redes e influenciadores
- **VOX MENSAGEM:** Geração de comunicações personalizadas e segmentadas
- **VOX GUARDIÃO:** Camada de compliance automatizada — monitora conformidade LGPD, detecta anomalias de acesso e protege dados sensíveis

Cada agente processa dados com **isolamento garantido**, sem acesso transversal automático. O **VOX GUARDIÃO** atua como guardião de conformidade, garantindo que violações de privacidade sejam detectadas e mitigadas automaticamente.

Dados territoriais são de fontes públicas (IBGE, DataSUS, INEP, etc.), mas **metadados de uso** (quem consultou o quê, quando, como) são tratados como **confidenciais e criptografados**, nunca sendo compartilhados sem consentimento.

Esta Política de Privacidade ("**Política**") explica como a Vox Civis coleta, processa, protege e utiliza dados pessoais de seus usuários, clientes e titulares de dados, em conformidade com:

- **Lei Geral de Proteção de Dados Pessoais** (LGPD — Lei nº 13.709/2018)
- **Regulamento Geral sobre Proteção de Dados** (GDPR — UE)
- **Lei de Privacidade do Consumidor** (CCPA — Califórnia, EUA)
- **ISO 27701** — Gestão da Privacidade
- **NIST Privacy Framework** — Governança de Privacidade

A Vox Civis compromete-se com a máxima transparência, segurança e proteção dos dados que gerencia.

---

## 2. Dados Coletados e Fontes

### 2.1 Categorias de Dados Pessoais

A Vox Civis coleta dados pessoais nas seguintes categorias:

#### **A. Dados de Identificação**
- Nome completo
- E-mail corporativo/pessoal
- Telefone
- CPF ou CNPJ conforme legislação aplicável
- Endereço completo (logradouro, número, complemento, CEP, cidade, estado)

#### **B. Dados de Acesso e Autenticação**
- Username/login
- Senha (armazenada com hash criptográfico)
- Tokens de sessão (armazenados em memória)
- Histórico de logins (data, hora, IP, navegador, device)
- Dados de MFA (autenticação multifator)

#### **C. Dados de Comportamento e Uso**
- Consultas realizadas na plataforma
- Relatórios acessados
- Agentes de IA utilizados (VOX RADAR, VOX PULSO, VOX CONEXÃO, VOX MENSAGEM, VOX GUARDIÃO)
- Filtros e parâmetros aplicados
- Tempo de sessão
- Cliques, interações, navegação
- Downloads e exportações
- Dados de geolocalização (quando explicitamente autorizado)

#### **D. Dados de Relacionamento e CRM**
- Histórico de contato (emails, telefonemas, reuniões)
- Anotações e notas internas
- Preferências comunicacionais
- Status de interação (prospect, cliente, churn)
- Dados de hiperpersonalização (segmentação comportamental)

#### **E. Dados Agregados e Públicos (Dados Territoriais)**
- Dados do IBGE (Instituto Brasileiro de Geografia e Estatística)
- Dados do DataSUS (Saúde Pública)
- Dados do INEP (Educação)
- Dados do SNIS (Saneamento)
- Dados do TSE (Eleições)
- Dados de 120+ fontes públicas adicionais
- *(Estes dados, por sua natureza pública, não são considerados dados pessoais de titulares específicos, mas podem ser combinados com dados pessoais para análise territorial)*

**Observação sobre Dados Territoriais vs. Metadados de Uso:**
- ✓ Dados territoriais (IBGE, DataSUS, etc.) são **públicos e não criptografados** para acesso rápido
- ✗ **Metadados de uso** (quem consultou qual análise, quando, por quantos minutos, com quais filtros) são tratados como **confidenciais e criptografados em repouso**
- ✗ Histórico de consultas nunca é compartilhado sem consentimento explícito
- ✗ Padrões de análise de usuários são segregados por cliente

#### **F. Dados Técnicos e de Infraestrutura**
- Endereço IP
- Tipo e versão de navegador
- Sistema operacional
- Device fingerprint
- Cookies de sessão
- User-Agent
- Logs de acesso e erro

#### **G. Dados de Conversas com IA**
- Prompts e consultas enviadas aos agentes de IA
- Respostas e recomendações geradas
- Metadados de interação (timestamp, duração, modelo utilizado)
- Feedback do usuário sobre qualidade de resposta

### 2.2 Dados Não Coletados

A Vox Civis **não coleta**, **não processa** e **não armazena**:

- Dados de menores de 18 anos sem consentimento parental/responsável legal
- Dados genéticos, biométricos ou de saúde sensível sem base legal explícita
- Dados de contas bancárias, cartões de crédito ou senhas
- Números de identidade (RG, CNH, Passaporte) sem necessidade operacional
- Imagens de câmera de vigilância (facial recognition)
- Comunicações privadas sem consentimento

---

## 3. Base Legal para o Processamento

Conforme artigos 7º e 11 da LGPD, o processamento de dados pessoais pela Vox Civis está fundamentado nas seguintes bases legais:

### **3.1 Consentimento (Art. 7º, I)**
- **Consentimento Operacional** (obrigatório): Para criar conta e utilizar a plataforma
- **Consentimento de Marketing** (opcional): Para enviar comunicações comerciais, newsletters, webinars
- Consentimento deve ser informado, específico, livre e inequívoco
- Pode ser retirado a qualquer momento

#### **Captura Prática de Consentimento**

**A. Banner de Cookies com Opções Granulares**
- Exibido ao primeiro acesso à plataforma
- Opções distintas:
  - ✓ Cookies Obrigatórios (autenticação, segurança) — ativados por padrão
  - ☐ Cookies de Preferências (idioma, tema)
  - ☐ Cookies de Analytics (comportamento, performance)
  - ☐ Cookies de Marketing (retargeting, publicidade)
- Botão "Aceitar Todos", "Rejeitar Tudo" e "Personalizar" claramente visíveis
- Consentimento granular armazenado imediatamente
- Pode ser revisto a qualquer momento via "Gerenciar Cookies" no rodapé

**B. Checkbox Separado para Marketing no Formulário de Cadastro**
- Formulário de registro apresenta checkboxes isolados:
  - ✓ Aceito os Termos e Política de Privacidade (obrigatório)
  - ☐ Desejo receber comunicações de marketing, novidades e ofertas especiais (opcional)
  - ☐ Autorizo o uso de dados ANONIMIZADOS de minhas consultas para análise de padrões agregados e refinamento dos agentes especializados e funcionalidades da plataforma VoxCivis. A operacionalização desta autorização ocorrerá em fase posterior do produto, mediante aviso prévio de 30 dias. Eventuais novos agentes ou produtos incluídos na plataforma serão comunicados na mesma forma e abrangidos por esta autorização, salvo revogação expressa. Pode ser revogada a qualquer momento no Centro de Preferências (opcional)
- Cada checkbox é independente
- Texto claro explicando cada finalidade, escopo dos dados e tempo de ativação
- Padrão: desmarcados (opt-in, não opt-out)

**C. Centro de Preferências Acessível**
- Link "Gerenciar Preferências de Privacidade" no rodapé de toda página
- Acessível também no menu de usuário autenticado
- Dashboard de autoatendimento com:
  - Visualização do consentimento atual
  - Histórico de alterações de consentimento (datas e versões)
  - Opção de revogar/atualizar consentimento a qualquer momento
  - Exportação de comprovante de consentimento (PDF)
- Alterações aplicadas imediatamente

**D. Registro Imutável de Cada Consentimento**
- Cada ato de consentimento (ou revogação) registra automaticamente:
  - **Timestamp:** Data e hora exata (fuso horário)
  - **IP do Usuário:** Endereço de origem
  - **Versão dos Termos:** Versão da Política de Privacidade vigente no momento
  - **Tipo de Consentimento:** Operacional, marketing, analytics, IA
  - **Método de Captura:** Banner, formulário de signup, centro de preferências
  - **Status:** Ativo/Revogado
- Registros armazenados em log imutável (append-only)
- Comprovante disponível ao titular em qualquer momento
- NUNCA são alterados retroativamente (auditoria completa)

### **3.2 Contrato (Art. 7º, II)**
- Processamento necessário para execução de contrato de serviço SaaS
- Dados de identificação, autenticação e comportamento de uso

### **3.3 Obrigação Legal (Art. 7º, III)**
- Compliance com legislações fiscais, trabalhistas e anticorrupção
- Retenção de registros contábeis (conforme Art. 5º da Lei nº 8.666/93)

### **3.4 Legítimo Interesse (Art. 7º, IX)**
- Segurança da plataforma e prevenção de fraude
- Análise de comportamento para melhoria de serviço
- Comunicação operacional (avisos de segurança, manutenção)
- Testes de modelo de IA com dados anonimizados

### **3.5 Dados Sensíveis (Art. 11)**
Se aplicável (exemplo: pesquisas sociodemográficas com recorte de raça/gênero):
- Base: pesquisa científica ou políticas públicas
- Consentimento específico ou isenção de consentimento conforme legislação

---

## 4. Finalidades do Processamento

### **4.1 Finalidades Operacionais**
1. **Provisão de Serviço**: Permitir acesso à plataforma de inteligência territorial
2. **Autenticação e Segurança**: Verificar identidade, prevenir acesso não autorizado, detectar fraude
3. **Análise e Inteligência**: Processar consultas de dados, gerar relatórios, alimentar agentes de IA
4. **Manutenção Técnica**: Logs de erro, performance monitoring, debugging
5. **Suporte ao Cliente**: Responder dúvidas, resolver problemas, fornecer treinamento

### **4.2 Finalidades de Negócio**
1. **Hiperpersonalização**: Dados comportamentais alimentam CRM e retroalimentam modelo de IA para melhor recomendação
2. **Segmentação**: Identificar perfis de usuário, necessidades, preferências comunicacionais
3. **Análise de Uso**: Compreender quais agentes (RADAR, PULSO, etc.) agregam mais valor
4. **Billing e Faturamento**: Registrar uso para cobrança

### **4.3 Finalidades de Compliance**
1. **Atendimento a Requisições Legais**: Autoridades, órgãos reguladores, polícia
2. **Proteção de Direitos**: Cumprimento de obrigações contratuais, defesa legal
3. **Auditoria e Governança**: Registros de acesso, trilhas de auditoria
4. **Retenção Fiscal**: Manutenção de registros contábeis conforme exigências legais

### **4.4 Finalidades de Pesquisa e Melhoria**
1. **Treinamento de IA**: Anonimização de conversas para refinar modelos de linguagem (somente dados anonimizados — vide seção 11)
2. **Análise de Satisfação**: Pesquisas, NPS, feedback de usuário
3. **Desenvolvimento de Produtos**: Testes A/B, novas funcionalidades

---

## 5. Compartilhamento de Dados

### **5.1 Com Quem Compartilhamos**

#### **A. Prestadores de Serviço (Processadores)**
A Vox Civis compartilha dados com fornecedores terceirizados que atuam como processadores:

- **Infraestrutura e E-mail:** Hostinger (Brasil) — servidor dedicado com containers Docker; e-mails @voxcivis.ai via SMTP do Hostinger
- **Autenticação:** Keycloak (auto-hospedado · open-source) — OAuth2/OIDC
- **Login social:** Google (OAuth2 · apenas e-mail e nome)
- **Modelos de IA (LLM):** Anthropic, PBC e OpenAI, LLC — vide Seção 11.5
- **Pagamentos:** Asaas (Brasil) — gateway PCI-DSS compliant
- **Analytics privacy-friendly:** Plausible (UE) — sem fingerprinting · sem dados pessoais
- **Monitoramento de erros:** Sentry — logs sem PII
- **Backups:** internos no próprio servidor Hostinger, criptografados

> 📌 **Nota:** A inclusão de novos processadores (CRM, e-mail transacional dedicado, BI) será comunicada com 30 dias de antecedência via atualização desta Política.

Todos os processadores assinam Acordos de Processamento de Dados (DPA — Data Processing Agreement) garantindo:
- Conformidade LGPD/GDPR
- Confidencialidade e segurança
- Restrição de uso aos fins contratados
- Notificação de incidentes

#### **B. Autoridades Governamentais**
Compartilhamos dados quando exigido por lei:
- Ordem judicial ou administrativa
- Requisição do Ministério Público
- Investigação de atividades ilícitas
- Cumprimento de obrigações fiscais/regulatórias

#### **C. Parceiros Comerciais**
Somente com consentimento explícito:
- Integrações com plataformas parceiras (SIG, ERP, CRM)
- Programas de afiliados
- Estudos de caso (sempre anonimizados)

#### **D. Sucessores na Fusão/Aquisição**
Em caso de fusão, aquisição ou venda de ativos, dados podem ser transferidos a sucessor, respeitando direitos dos titulares.

### **5.2 Com Quem NÃO Compartilhamos**

A Vox Civis **NÃO compartilha**:
- Senhas (mesmo com prestadores de serviço)
- Conversas de clientes com agentes de IA (sem anonimização)
- Dados de CRM sensível (observações confidenciais)
- Dados pessoais para fins comerciais/publicidade sem consentimento explícito

### **5.3 Transferência Internacional**

Se dados forem processados fora do Brasil:
- **Cláusulas Contratuais Padrão** (SPCs) da LGPD/GDPR
- **Adequação de Proteção**: Confirmação de nível equivalente de proteção
- **Consentimento Específico**: Se aplicável, solicitado ao titular

---

## 6. Retenção de Dados

### **6.1 Prazos de Retenção por Categoria**

| Categoria | Prazo | Justificativa |
|-----------|-------|---------------|
| **Dados de Identificação** | Duração da relação contratual + 5 anos | Obrigações fiscais e legais |
| **Autenticação (Senhas)** | Duração da conta + 30 dias | Segurança de transição |
| **Histórico de Logins** | 24 meses | Auditoria de segurança |
| **Dados de Comportamento/Uso** | 3 anos | Análise de tendências |
| **Conversas com IA** | 2 anos (não anonimizadas); indeterminado se anonimizadas | Conformidade LGPD; treinamento de modelo |
| **Dados de CRM** | Duração da relação comercial + 2 anos | Histórico de relacionamento |
| **Logs de Acesso/Erro** | 12 meses | Segurança e debugging |
| **Backups** | 12 meses (com rotação mensal) | Recuperação de desastres |
| **Dados Agregados/Públicos** | Indeterminado (não vinculados a pessoa física específica) | Fonte de dados territorial |
| **Registros Contábeis** | 5 anos | art. 195 do Código Tributário Nacional (Lei 5.172/66) |

### **6.2 Exclusão de Dados**

Ao término do prazo de retenção ou a pedido do titular (direito ao esquecimento):
- Dados são **excluídos de forma irreversível** mediante destruição segura (zero fill, degausso, fragmentação)
- Cópias residuais em backups são incluídas conforme política de retenção
- Anonimização é mantida indefinidamente (não é identificável)
- Comprovante de exclusão pode ser solicitado

---

## 7. Direitos do Titular de Dados (LGPD — Artigo 18)

Qualquer pessoa cujos dados sejam processados pela Vox Civis possui os seguintes direitos:

### **7.1 Direito de Acesso (Art. 18, I)**
- Obter confirmação de processamento
- Acessar cópia de seus dados pessoais
- Conhecer origem dos dados
- Prazo para resposta: **até 15 dias** (prorrogável por mais 15 dias em casos complexos)
- **Formato de Resposta:** Dados exportados em formato estruturado:
  - JSON (recomendado para importação em sistemas)
  - CSV (compatível com planilhas)
  - PDF (legível, com sumário)
  - Escolha do formato conforme preferência do titular
- **Confirmação por Email:** Após preparação, email enviado ao titular com link de download seguro (válido por 30 dias)
- **Verificação de Identidade:** Pode ser solicitada para confirmar acesso

### **7.2 Direito de Retificação (Art. 18, II)**
- Corrigir dados imprecisos, incompletos ou desatualizados
- Direito a ser informado sobre correção realizada
- Prazo: **até 15 dias**

### **7.3 Direito à Exclusão (Art. 18, III)**
- Solicitar exclusão de dados (direito ao esquecimento)
- Exceções: obrigações legais, defesa legal, pesquisa científica anonimizada
- Prazo: **até 15 dias**

### **7.4 Direito à Portabilidade (Art. 18, IV)**
- Obter cópia de dados em formato estruturado e interoperável
- Transmitir dados a outro controlador
- Prazo: **até 30 dias**

### **7.5 Direito de Oposição (Art. 18, V)**
- Opor-se ao processamento baseado em legítimo interesse
- Opor-se a comunicações comerciais (marketing)
- Prazo: **até 15 dias**

### **7.6 Direito a Não Ser Submetido a Decisão Automatizada (Art. 18, VI)**
- Não ser submetido a decisão automatizada que produza efeitos prejudiciais
- Exemplo: exclusão de conta por algoritmo sem revisão humana
- Direito a revisão manual e explicação

### **7.7 Direito de Anonimização (Art. 18, VII)**
- Solicitar anonimização de dados quando não há necessidade de retenção pessoalizada
- Prazo: **até 15 dias**

### **7.8 Como Exercer os Direitos**

#### **Canal de exercício de direitos (vigente no MVP)**

Os titulares exercem seus direitos LGPD diretamente com o Encarregado de Dados:

- **E-mail:** <dpo@voxcivis.ai>
- **Resposta:** confirmação de recebimento em 2 dias úteis
- **Prazo final:** até 15 dias (prorrogável por mais 10 dias mediante justificativa · LGPD art. 19)
- **Verificação de identidade:** pode ser solicitada por segurança

> 📌 **Roadmap:** portal de autoatendimento com painel de direitos · prazo previsto Q3/2026


#### **Identificação para verificação (LGPD art. 9º)**

Para solicitações que exijam verificação de identidade do titular:

**E-mail principal (DPO):** <dpo@voxcivis.ai>
**E-mail atendimento geral:** <atendimento@voxcivis.ai>
**Sede:** Brasília/DF, Brasil
**CNPJ:** 59.999.302/0001-68


**Informações a Fornecer:**
- Nome completo e CPF/CNPJ
- Email registrado na plataforma
- Descrição clara do direito a exercer
- Evidência de identidade (cópia de documento — CNH, RG, passaporte)
- Assinatura eletrônica ou física

**Compromisso:** 
- Confirmação de recebimento: 2 dias úteis
- Resposta completa: até 15 dias (prorrogável por mais 15 em casos complexos)
- Comunicação em Português garantida

---

## 8. Cookies e Tecnologias de Rastreamento

### **8.1 Tipos de Cookies Utilizados**

| Tipo | Finalidade | Duração | Consentimento |
|------|-----------|---------|---------------|
| **Sessão (Obrigatório)** | Autenticação, manutenção de login | Até logout | Não (operacional) |
| **Preferências** | Idioma, tema, tamanho de fonte | 12 meses | Sim |
| **Segurança** | CSRF protection, rate limiting | Duração da sessão | Não (obrigatório) |
| **Analytics** | Comportamento de uso, performance | 24 meses | Sim |
| **Marketing** | Retargeting, publicidade programática | 30 dias | Sim |

### **8.2 Consentimento de Cookies**

- **Cookies Operacionais** (autenticação, segurança): Implícitos, não requerem consentimento
- **Cookies de Terceiros** (analytics, marketing): Requerem consentimento explícito via banner
- Banner de cookie é exibido ao primeiro acesso
- Consentimento é armazenado por 12 meses
- Pode ser revogado a qualquer momento

### **8.3 Rastreamento de Terceiros**

Ferramentas de analytics/marketing podem depositar cookies independentes:
- **Plausible Analytics** (privacy-friendly · sediado na União Europeia · sem fingerprinting · sem dados pessoais)
- **Sentry** (captura de erros JavaScript · sem PII)
- A VoxCivis **não utiliza** Google Analytics, Facebook Pixel, Hotjar ou ferramentas similares de rastreamento publicitário
- Consulte políticas de privacidade desses terceiros
- A Vox Civis não controla essas cookies

### **8.4 Do Not Track (DNT)**

Se navegador estiver configurado com DNT:
- VoxCivis respeita a preferência
- Analytics de terceiros podem não respeitar (responsabilidade deles)

---

## 9. Segurança dos Dados

A segurança e a proteção dos dados são **pilares fundamentais** da arquitetura VoxCivis, integrados desde a concepção da plataforma (*Security by Design*). A SIAS adota controles alinhados às **melhores práticas de mercado aplicáveis ao estágio atual** do produto, com plano formal de evolução contínua à medida que a operação amadurece.

Esta Política compromete-se com **transparência integral**: declara explicitamente o que está implementado em produção e o que está planejado para evolução, sem ambiguidade.

### 9.1 Pilares de segurança em produção (arquitetura V3.9)

A plataforma VoxCivis opera sobre uma **arquitetura de classe enterprise** validada por padrões consolidados de mercado. Cada componente foi escolhido por sua robustez, maturidade e adoção em organizações sensíveis (financeiras, governo, saúde).

#### A. Identidade e autenticação centralizada

A gestão de identidade segue o padrão **OAuth2 / OpenID Connect** — referência adotada por bancos, plataformas governamentais e provedores de cloud de classe mundial.

- **Servidor de identidade:** Keycloak (auto-hospedado · realm dedicado `voxcivis`)
- **Tokens:** JWT assinados, validados a cada requisição via cache JWKS
- **Hash de senhas:** algoritmos criptográficos modernos (gerenciados pelo Keycloak)
- **Princípio do menor privilégio** aplicado a todos os acessos administrativos

#### B. Criptografia em trânsito de ponta a ponta

Todo o tráfego entre cliente, plataforma e fornecedores externos é criptografado com **TLS** atualizado e certificados gerenciados automaticamente.

- **Edge:** Traefik com TLS automático (renovação Let's Encrypt)
- **Domínios cobertos:** `api.voxcivis.ai`, `auth.voxcivis.ai`, `legal.voxcivis.ai`
- **Comunicação com LLMs externos:** HTTPS sob DPA de não-treinamento (Seção 11.5)

#### C. Auditoria completa e rastreável

Cada requisição à plataforma é registrada de forma **imutável** com retenção compatível com a legislação aplicável.

- **Audit log** em PostgreSQL com retenção de **5 anos** (LGPD)
- Captura via `AuditMiddleware` no Gateway · modo *fire-and-forget* (zero impacto em latência)
- **Estrutura padronizada:** timestamp, usuário (claim do JWT), agente alvo, decisão do GUARDIÃO
- Rastreabilidade ponta-a-ponta de cada interação com agentes de IA

#### D. Controle de tráfego e proteção contra abuso

Mecanismos de **rate-limiting em múltiplas camadas** protegem a plataforma e os usuários contra uso abusivo, ataques de força bruta e exfiltração massiva.

- **3 níveis temporais:** segundo · minuto · dia
- Aplicação dual: por **usuário** (claim JWT) e por **IP** (camada externa)
- Contadores em Redis · resposta padrão `429 Too Many Requests`

#### E. Compliance automatizado: VOX GUARDIÃO

Diferencial arquitetural da VoxCivis: **toda saída de IA passa por um gate de compliance automatizado** antes de chegar ao usuário.

- **Workflow dedicado** (n8n WF-02) executado em 100% das respostas
- **Watermark automático** em toda resposta aprovada (rastreabilidade de autoria)
- **Bloqueio ativo** de conteúdo potencialmente eleitoral (Lei 9.504/97)
- Decisões registradas no audit log para auditoria

#### F. Infraestrutura controlada e isolada

- **Hospedagem em território nacional** (Hostinger Brasil · servidor dedicado)
- Orquestração via Easypanel · **rede Docker isolada** (`easypanel-vox_civis`)
- Componentes containerizados: Edge (Traefik) · Identidade (Keycloak) · Gateway (FastAPI) · Persistência (PostgreSQL) · Cache (Redis) · Orquestração de agentes (n8n) · Interface admin (OpenWebUI)
- **Soberania de dados:** dados de clientes residem em território brasileiro

#### G. Pipeline da requisição (defense in depth)

A ordem dos controles é parte do design — princípio **fail-fast**: validações ocorrem **antes** de qualquer chamada ao LLM, minimizando exposição.

```
Cliente → Traefik (TLS) → Gateway FastAPI →
   CORS → Auth (JWKS) → Rate-limit (Redis) → Audit (Postgres) →
   Roteamento → Agente (n8n WF-01) → LLM (Anthropic / OpenAI) →
   GUARDIÃO (n8n WF-02) → Watermark → Cliente
```

#### H. Política de não-uso de dados para treinamento

- **Nenhuma conversa de cliente é utilizada para treinar modelos** (vide Seção 11)
- Anthropic e OpenAI fornecem **garantia contratual via DPA** de não-treinamento
- Modelos acessados via API empresarial · sem retenção além do mínimo operacional

### 9.2 Frameworks e referências de mercado adotados

A arquitetura VoxCivis é construída tendo como **referência** os seguintes frameworks consolidados, aplicados na medida adequada ao estágio atual da operação:

- **LGPD** (Lei 13.709/2018) — base legal da proteção de dados pessoais · **conformidade implementada**
- **Marco Civil da Internet** (Lei 12.965/2014) — **conformidade implementada**
- **OWASP Top 10** — referência para mitigação de vulnerabilidades em aplicação web · **adotado no design**
- **ISO 27001 / ISO 27701** — referências para gestão de segurança e privacidade · adotadas como **norte arquitetural** · certificação formal no plano de evolução
- **NIST Cybersecurity Framework** — referência para postura defensiva · **incorporado nas decisões de arquitetura**

### 9.3 Plano de Evolução Contínua

A SIAS opera com **transparência integral** sobre seu plano de amadurecimento de segurança. Os controles abaixo **não estão implementados no MVP** (lançamento 18/05/2026) e seguem cronograma formal de implementação proporcional ao crescimento da operação. Esta Política será atualizada à medida que cada item entrar em produção.

**Horizonte 1 (até Q3/2026)**

- Autenticação multifator (MFA) disponível por plano comercial
- Login social via Google e Microsoft (OAuth2)
- Criptografia em repouso (PostgreSQL TDE / criptografia de volume)
- Backups com gerenciamento de chave separado
- Row-Level Security (RLS) no PostgreSQL para isolamento multi-tenant
- Storage objeto S3-compatible (MinIO) para PDFs e relatórios
- Sistema de alertas em tempo real para a equipe de operações

**Horizonte 2 (12-18 meses)**

- HSM/KMS gerenciado para chaves criptográficas
- WAF (Web Application Firewall) dedicado
- SIEM (Security Information and Event Management) com correlação
- Detecção de anomalias com aprendizado de máquina
- Pen test anual por terceiro independente certificado

**Horizonte 3 (12-24 meses)**

- ISMS (Information Security Management System) formal baseado em ISO 27001
- Comitê de Segurança colegiado
- Background check estruturado para posições sensíveis
- **Certificações:** ISO 27001 · ISO 27701 · SOC 2 Type II

### 9.4 Resposta a incidentes de segurança

A SIAS mantém procedimento formal de resposta a incidentes alinhado ao **art. 48 da LGPD**:

1. **Detecção e contenção** imediatas via monitoramento da arquitetura
2. **Avaliação de severidade** pelo Encarregado de Dados (DPO)
3. **Notificação à ANPD** em até **72 horas** quando houver risco aos titulares
4. **Comunicação aos titulares afetados** em linguagem clara e tempestiva
5. **Análise de causa raiz** documentada no audit log (5 anos)
6. **Remediação e prevenção** de recorrência

**Canal de reporte:** <dpo@voxcivis.ai>

### 9.5 Reporte responsável de vulnerabilidades

A SIAS valoriza pesquisadores de segurança e a comunidade técnica. Vulnerabilidades identificadas devem ser reportadas a <dpo@voxcivis.ai> sob **disclosure responsável**:

- Não exploramos, não retaliamos
- Reconhecemos publicamente colaborações relevantes (com autorização)
- Compromisso de remediação proporcional à severidade


## 10. Privacy by Design e Privacy by Default (Art. 46 §2º LGPD)

A Vox Civis implementa privacidade como princípio fundamental em toda arquitetura e operação.

### **10.1 Privacy by Design — Privacidade desde a Concepção**

Toda decisão de engenharia e produto integra proteção de dados:

**A. Minimização de Dados**
- ✓ Coletar apenas dados necessários para cada funcionalidade
- ✓ Não coletar "para o futuro" — principle of purpose limitation (finalidade limitada)
- ✓ Exemplo: Para análise de saúde municipal, coleta-se dados do DataSUS agregados, não dados pessoais de pacientes
- ✓ Auditoria trimestral de campos coletados vs. campos utilizados

**B. Segregação por Agente de IA**
- ✓ Cada agente (RADAR, PULSO, CONEXÃO, MENSAGEM, GUARDIÃO) opera com acesso isolado aos dados necessários
- ✓ Não há acesso transversal automático entre agentes
- ✓ Dados de CRM segregados de dados públicos
- ✓ Conversas de um cliente não acessam conversas de outro
- ✓ VOX GUARDIÃO atua como camada de compliance automatizada, monitora isolamento

**C. Pseudonimização desde a Origem**
- ✓ Dados pessoais identificáveis são pseudonimizados em banco de dados
- ✓ Identificadores armazenados separadamente com criptografia adicional
- ✓ Re-identificação requer múltiplas chaves e logs de auditoria

**D. Retenção Mínima**
- ✓ Políticas de retenção definidas durante design (não após coleta)
- ✓ Exclusão automática ao fim do prazo via scheduler
- ✓ Retenção mínima necessária = padrão, não máxima

**E. DPIA (Data Protection Impact Assessment) Obrigatória**
- ✓ Antes de implementar novo agente de IA
- ✓ Antes de integrar nova fonte de dados
- ✓ Antes de mudanças significativas em infraestrutura
- ✓ DPIA inclui análise de riscos e medidas de mitigação
- ✓ Resultado disponível ao DPO e solicitável pelos titulares

### **10.2 Privacy by Default — Privacidade como Padrão**

Todas as configurações padrão favorecem proteção máxima:

**A. Consentimento Opt-in (Não Opt-out)**
- ✓ Marketing desativado por padrão (usuário escolhe ativar)
- ✓ Analytics de comportamento desativado por padrão
- ✓ Compartilhamento com parceiros exige consentimento explícito
- ✓ Anonimização para treinamento de IA é opt-in

**B. Visibilidade e Controle**
- ✓ Dashboard de privacidade visível por padrão no menu
- ✓ Histórico de consentimento acessível em um clique
- ✓ Preferências de comunicação destacadas no perfil

**C. Proteção Máxima para Dados Sensíveis**
- ✓ Conversas com IA: criptografia end-to-end (padrão)
- ✓ Dados de CRM: criptografia em BD (padrão)
- ✓ Acesso a CRM: requer MFA (padrão)
- ✓ Logs de acesso a dados sensíveis: imutáveis e auditados (padrão)

**D. Retenção Reduzida por Padrão**
- ✓ Conversas: 2 anos (não indeterminado)
- ✓ Logs: 12 meses (não perpétuo)
- ✓ Cookies: 24 meses máximo (não sem limite)
- ✓ Backups: 12 meses com rotação mensal (não mantém todas as versões)

---

## 11. Anonimização e Pseudonimização para Treinamento de IA

### **11.0 Status atual e modelo de consentimento adotado (vigente desde 18/05/2026)**

**Estado operacional atual.** A VoxCivis **NÃO realiza** atualmente, e até segunda comunicação, qualquer uso de dados de clientes para treinamento, retreinamento ou refinamento de modelos de IA. Os modelos de linguagem (LLMs) utilizados são pré-treinados pelos fornecedores externos e acessados como serviço, sem retreinamento pela VoxCivis.

**Modelo de consentimento adotado.** Adotamos modelo de **consentimento opt-in granular com ativação futura**. Isso significa que:

1. **Coleta antecipada do consentimento.** No momento do cadastro, o usuário pode autorizar voluntariamente, em checkbox isolado e desmarcado por padrão (Seção 3.1.B), o uso futuro de seus dados anonimizados para refinamento dos agentes especializados da plataforma.

2. **Ativação condicionada.** A operacionalização efetiva desta autorização **somente ocorrerá em fase posterior do produto**, mediante:
   - Aviso prévio de **30 dias** ao usuário, por e-mail e banner no site
   - Atualização desta Política descrevendo o pipeline técnico de anonimização adotado
   - Possibilidade de revogação imediata pelo Centro de Preferências antes da ativação
   - Confirmação técnica de irreversibilidade da anonimização (k-anonymity ≥ 5, conforme Seção 11.4)

3. **Direito de revogação.** A autorização concedida no cadastro pode ser revogada a qualquer momento, antes ou depois da ativação operacional, sem qualquer prejuízo ao acesso ou uso do serviço pelo usuário.

4. **Especificidade do consentimento.** A finalidade é específica — refinamento dos agentes especializados e funcionalidades atualmente disponíveis na plataforma VoxCivis (na data desta Política: RADAR, PULSO, CONEXÃO, MENSAGEM e GUARDIÃO).

5. **Evolução do produto.** A VoxCivis poderá, ao longo do tempo, incluir novos agentes especializados e produtos premium em sua plataforma. Quando isso ocorrer:
   - Esta Política e a comunicação ao titular serão atualizadas com **30 dias de antecedência**, descrevendo o novo agente ou produto, sua finalidade e o tipo de dado tratado
   - O consentimento previamente concedido pelo titular permanece válido para os novos agentes e funcionalidades **estritamente equivalentes** em natureza e finalidade aos já existentes (refinamento via dados anonimizados)
   - Qualquer **novo tipo de tratamento materialmente distinto** (ex.: uso de dados não-anonimizados, transferência a novos terceiros, finalidades não comerciais, dados sensíveis) exigirá **novo consentimento específico** do titular
   - O titular tem o direito de revogar a autorização a qualquer momento, antes ou depois da inclusão de novos agentes

**Justificativa do modelo.** Esta abordagem visa equilibrar (a) a transparência exigida pelo art. 8º §4º da LGPD com (b) a praticidade operacional para o titular, evitando reabordagem futura. Caso a redação ou estrutura desse consentimento seja questionada, a VoxCivis acatará determinação da ANPD ou recomendação de seu Encarregado.

**Subseções 11.1 a 11.5.** As subseções a seguir descrevem em detalhe os fundamentos técnicos da anonimização, os fornecedores externos de IA e suas garantias contratuais de não-uso para treinamento.

### **11.1 Diferenças Conceituais**

- **Anonimização:** Remoção irreversível de identificadores → dados não são mais pessoais
- **Pseudonimização:** Substituição de identificadores por código → dados permanecem pessoais, mas vinculados indiretamente

### **11.2 Uso de Dados para Treinar IA**

#### **A. Dados Anonimizados (Permitido)**
- Conversas antigas (>2 anos) são automaticamente anonimizadas
- Processo de anonimização:
  1. Remoção de nomes, e-mails, CPF, telefone
  2. Remoção de dados de localização específica
  3. Generalização de datas (apenas mês/ano)
  4. Aplicação de k-anonymity (mínimo 5 registros similares)
- Dados anonimizados são **irreversivelmente desvinculados** do titular
- Utilizados para:
  - Refino de modelos de linguagem (LLM)
  - Treinamento de agentes de IA (RADAR, PULSO, etc.)
  - Análise de tendências agregadas
- **Sem consentimento adicional** necessário (são dados anonimizados)

#### **B. Dados Pseudonimizados (Restrito)**
- Conversas recentes (<2 anos) podem ser pseudonimizadas para análise
- Código substitui identificador direto
- **Consentimento explícito necessário** durante onboarding
- Acesso restrito a equipe técnica
- Reversão (re-identificação) requer múltipla aprovação
- Prazo máximo: 2 anos

#### **C. Dados Não-Anonimizados (Proibido)**
- Conversas/CRM identificáveis **NÃO são utilizadas** para treinar IA pública
- Acesso apenas para suporte ao cliente (com consentimento)
- Deletadas conforme política de retenção

### **11.3 Transparência e Controle**

- Usuário é informado durante signup: "Seus dados anonimizados podem treinar a IA"
- Consentimento de marketing/pesquisa é separado (pode ser revogado)
- Dashboard de privacidade permite:
  - Ver quais conversas foram anonimizadas
  - Solicitar anonimização antecipada
  - Optar-se do treinamento de IA

### **11.4 Tecnologias de Anonimização (Roadmap técnico)**

> 📌 **Roadmap (não ativo hoje):** Quando o uso de dados anonimizados para refino dos agentes for ativado (vide Seção 11.0), as seguintes técnicas serão aplicadas:

- **Differential Privacy:** Adiciona ruído matemático para impedir re-identificação
- **K-Anonymity:** Mínimo de 5 registros similares
- **L-Diversity:** Diversidade de atributos sensíveis
- **Data Masking:** Mascaramento de PII (Personally Identifiable Information)

### **11.5 Fornecedores Externos de IA (Operadores LGPD)**

A VoxCivis utiliza modelos de linguagem de fornecedores externos para processar consultas dos usuários. Os fornecedores atuais são:

- **Anthropic, PBC** (Estados Unidos) — modelos Claude (Sonnet, Haiku) acessados via API
- **OpenAI, LLC** (Estados Unidos) — modelos GPT (GPT-4o, GPT-4o-mini) acessados via API

**Política de não-uso para treinamento.** Ambos os fornecedores, conforme termos contratuais aplicáveis ao acesso por API empresarial:
- **NÃO utilizam** os dados das consultas (inputs) nem das respostas (outputs) para treinar ou aprimorar seus próprios modelos
- **NÃO retêm** o conteúdo das consultas após o processamento, exceto pelo período mínimo necessário para detecção de abuso (até 30 dias)
- **NÃO compartilham** o conteúdo com terceiros para fins de treinamento

Esta garantia está formalizada nos Data Processing Addenda (DPAs) firmados com cada fornecedor, disponíveis para consulta mediante solicitação ao DPO em <dpo@voxcivis.ai>.

**Transferência internacional de dados.** Considerando que ambos os fornecedores realizam o processamento nos Estados Unidos, aplica-se o disposto nos artigos 33 a 36 da LGPD:
- A transferência ocorre com base em cláusulas contratuais específicas que oferecem nível de proteção adequado (art. 33, II)
- O usuário é informado sobre a transferência internacional ao aceitar esta Política
- O usuário pode solicitar informações detalhadas sobre o fluxo de dados internacionais via canal do titular

**Componentes auto-hospedados (não são operadores externos).** Outros componentes da plataforma — como **OpenWebUI** (interface admin/dogfooding), **Keycloak** (autenticação), **PostgreSQL** (banco e audit_log), **Redis** (cache e rate-limit) e **n8n** (orquestração dos agentes WF-01/WF-02) — são software open-source executados em infraestrutura controlada pela VoxCivis (servidor Hostinger no Brasil). Não há transferência a terceiros nesses componentes; eles fazem parte do ambiente operacional do controlador.

**Substituição ou inclusão de fornecedores.** Caso a VoxCivis venha a substituir ou incluir novos fornecedores externos de IA, esta Política será atualizada com 30 dias de antecedência, e novo consentimento será solicitado quando aplicável conforme o art. 9º §2º da LGPD.

---

## 12. Menores de 18 Anos

### **12.1 Restrições**

A Vox Civis **não intenciona** coletar dados de menores de 18 anos.

Se descobrir que dados de menor foram coletados:
1. Notificação imediata ao responsável legal
2. Exclusão dos dados em até 15 dias
3. Avaliação de base legal de coleta

### **12.2 Dados Agregados de Menores**

Análises demográficas que incluem dados de menores (ex.: "população escolar por município"):
- Utiliza dados públicos agregados (INEP, IBGE)
- Não permite identificação de menores específicos
- Não requer consentimento parental (dados anonimizados/agregados)

### **12.3 Responsabilidade Parental**

Se maior de idade contrata plataforma para fins comerciais/educacionais:
- Responsável legal deve consentir
- Monitoramento técnico pode ser implementado
- Dados de acesso devem ser segregados

---

## 13. Controlador e Encarregado de Proteção de Dados (DPO)

### **13.1 Controlador**

- **Razão Social:** SIAS - Soluções em Inteligência Artificial e Sustentabilidade LTDA
- **CNPJ:** 59.999.302/0001-68
- **Sede:** Brasília/DF, Brasil
- **E-mail institucional:** <atendimento@voxcivis.ai>
- **Sócio-Administrador:** Francisco de Assis Ferreira Braga Filho

### **13.2 Encarregado de Proteção de Dados (DPO — Data Protection Officer)**

- **Nome:** Francisco de Assis Ferreira Braga Filho
- **Função:** Encarregado de Proteção de Dados (DPO interino · pendente nomeação formal por instrumento societário)
- **E-mail dedicado:** <dpo@voxcivis.ai>
- **Endereço para correspondência:** SIAS LTDA · Brasília/DF, Brasil

**Responsabilidades do DPO:**
- Monitorar conformidade com LGPD
- Ponto de contato para autoridade (ex.: ANPD — Autoridade Nacional de Proteção de Dados)
- Apoiar exercício de direitos de titulares
- Coordenar avaliações de impacto
- Investigar denúncias de violação

---

## 14. Auditoria e Conformidade de Terceiros (Processadores)

A Vox Civis implementa rigorosa governança sobre prestadores de serviço que processam dados pessoais.

### **14.1 Due Diligence Antes de Contratação**

Antes de integrar qualquer processador, a Vox Civis realiza:

- **Avaliação de Segurança:** Verificação de certificações (ISO 27001, SOC 2, etc.)
- **Avaliação de Conformidade:** Garantia de aderência a LGPD/GDPR
- **Verificação de Histórico:** Antecedentes de incidentes de segurança
- **Análise de Jurisdição:** Confirmação de nível de proteção de dados adequado
- **Referências:** Consulta com outros clientes e análise de reputação
- **Documentação:** Solicitação de políticas de privacidade, termos de serviço, certificados

### **14.2 Data Processing Agreement (DPA) — Obrigatório**

Todo processador assina **Acordo de Processamento de Dados** incluindo:

**Responsabilidades do Processador:**
- ✓ Processar dados apenas conforme instruções da Vox Civis (controlador)
- ✓ Garantir confidencialidade dos funcionários
- ✓ Implementar medidas técnicas e organizacionais equivalentes à Vox Civis
- ✓ Não compartilhar dados sem autorização explícita
- ✓ Notificar incidentes em até 24 horas
- ✓ Cooperar com autoridades regulatórias

**Cláusulas Críticas:**
- Obrigatoriedade de sub-processadores serem pré-aprovados
- Direito de auditoria contratual a qualquer momento
- Dever de confidencialidade mesmo após término do contrato
- Responsabilidade por danos causados por violação

### **14.3 Auditoria Periódica de Conformidade**

A Vox Civis realiza auditorias conforme critério de risco:

| Processador | Frequência | Método |
|-------------|-----------|--------|
| **Crítico** (hospedagem, backup, CRM) | Anual ou a cada incidente | Auditoria in-loco + questionário |
| **Alto** (analytics, email) | Anual | Questionário de conformidade |
| **Médio** (tools integrados) | Bienal | Verificação de certificação válida |
| **Baixo** (serviços pontuais) | Sob demanda | Revisar termos de serviço |

**Escopo da Auditoria:**
- Implementação de criptografia (em repouso e trânsito)
- Controles de acesso e autenticação
- Política de retenção de dados
- Plano de resposta a incidentes
- Conformidade com LGPD/GDPR
- Qualidade de backups e recuperação

### **14.4 Direito de Auditoria Contratual**

A Vox Civis reserva o direito de:

- **Auditar** instalações, sistemas e processos do processador (com aviso prévio de 15 dias)
- **Solicitar Certificados:** SOC 2 Type II, ISO 27001, GDPR Readiness (atualizado anualmente)
- **Entrevistar** equipe técnica e segurança
- **Testar** a recuperação de dados (disaster recovery test)
- **Revisar** logs de acesso e incidentes
- **Exigir Remediação:** Implementar ações corretivas em prazo acordado
- **Encerrar Contrato:** Se processador não se adequar a padrões

---

## 15. Avaliação de Impacto à Proteção de Dados (AIPD)

### **15.1 Quando Realizada**

A Vox Civis realiza Avaliação de Impacto à Proteção de Dados em:

- Implementação de novo agente de IA
- Integração com nova fonte de dados
- Mudança significativa em arquitetura de armazenamento
- Processamento de dados sensíveis em novo contexto
- Uso de lógica de decisão automatizada

### **15.2 Documentação**

AIPD inclui:
- Descrição do processamento
- Avaliação de necessidade e proporcionalidade
- Identificação de riscos
- Medidas de mitigação
- Consulta a DPO
- Registro em registro de processamento

### **15.3 Transparência**

Resumo de AIPD pode ser solicitado ao DPO.

---

## 16. Notificação de Incidentes

### **16.1 O Que É um Incidente**

Violação de segurança envolvendo:
- Perda de dados
- Acesso não autorizado
- Corrupção de dados
- Indisponibilidade

### **16.2 Procedimento de Notificação**

#### **Descoberta → Investigação (até 72h)**
1. Identificação e contenção do incidente (within 1 hour)
2. Avaliação de impacto
3. Análise de risco ao titular
4. Coleta de evidências e logs imutáveis

#### **Notificação ao Titular (Art. 34 LGPD)**
- **Se houver risco ao titular:** Notificação proativa e imediata por email/SMS
- **Linguagem Clara:** Evitar jargão técnico, explicar em português acessível:
  - O que aconteceu (descrição simples do incidente)
  - Quais dados foram afetados (categorias específicas)
  - Que medidas a Vox Civis tomou
  - O que o titular deve fazer para se proteger
  - Canal para dúvidas e suporte
- **Prazo:** Sem atraso injustificado (até 72h de confirmação de impacto)
- **Comprovante:** Oferecer monitoramento de crédito ou serviço de proteção conforme aplicável

#### **Notificação Proativa à ANPD (Art. 48 LGPD)**
- **Incidente com Risco ao Titular:** Comunicação OBRIGATÓRIA à ANPD em até **72 horas** da descoberta
- **Conteúdo do Aviso:**
  - Descrição detalhada do incidente
  - Dados pessoais afetados e volume de titulares
  - Avaliação de riscos ao titular
  - Medidas de mitigação adotadas ou planejadas
  - Contato do DPO para comunicação com ANPD
  - Comprovante de notificação aos titulares (se já realizada)
- **Canal:** Portal da ANPD (https://www.gov.br/cidadania/anpd) — Formulário de Notificação de Incidente
- **Incidentes Sem Risco Significativo:** Ainda assim registrados e documentados, mesmo que não reportáveis

#### **Registro de Todos os Incidentes**
- **Log Imutável:** Todos os incidentes, independente de risco, são registrados em trilha de auditoria permanente:
  - ID do incidente
  - Data/hora da descoberta
  - Data/hora da contenção
  - Tipo de incidente (acesso não autorizado, perda, corrupção, indisponibilidade)
  - Dados afetados
  - Avaliação de risco
  - Ações tomadas
  - Status de notificação (titular/ANPD)
- **Retenção:** Mínimo 5 anos para auditoria regulatória
- **Consulta:** DPO e autoridades podem consultar registro

#### **Comunicação Transparente**
- **Canal Oficial:** incidentes@voxcivis.ai
- **Página de Status:** status.voxcivis.ai
- **Comunicado à Imprensa:** Se impacto massivo (>1000 titulares ou dados sensíveis)
- **Pós-Incidente:** Disponibilizar relatório detalhado de causa raiz ao DPO e titulares

### **16.3 Direitos Após Incidente**

Titulares afetados têm direito a:
- Informação clara sobre o ocorrido
- Orientação de como se proteger
- Monitoramento de notificações sobre o caso
- Suporte do DPO para esclarecimento de dúvidas
- Recurso à ANPD caso julgue necessário

---

*Documento publicado em https://legal.voxcivis.ai/privacidade · Versão definitiva após validação por escritório especializado em LGPD.* 