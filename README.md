# 🚀 Software Engineer Portfolio

Bem-vindo ao meu portfólio de **Engenharia de Software**! Aqui você encontra uma seleção de projetos em **Python, APIs, Automação, Trading Algorítmico** e muito mais.

## 📋 Índice

- [Sobre](#sobre)
- [Mapa dos Projetos](#-mapa-dos-projetos)
- [Projetos Privados](#projetos-privados)
- [Projetos Públicos](#projetos-públicos)
- [Produtos & Clientes em Produção](#-produtos--clientes-em-produção)
- [Engenharia de Validação e Segurança](#-engenharia-de-validação-e-segurança)
- [Stack de Tecnologias](#stack-de-tecnologias)
- [Como Acessar Repositórios Privados](#como-acessar-repositórios-privados)
- [Contribuições & Colaboradores](#contribuições--colaboradores)

---

## 👨‍💻 Sobre

Sou um **Software Engineer** apaixonado por desenvolver soluções robustas e escaláveis. Meus projetos focam em:

✅ **Automação e Trading Algorítmico** - Bots inteligentes com Python e MetaTrader5  
✅ **Machine Learning aplicado a trading** - Modelos LightGBM/ONNX executando dentro do MQL5, validação walk-forward e controles anti-overfit  
✅ **APIs e Integração de Sistemas** - RESTful APIs, WebSockets, Data Pipeline  
✅ **Python Avançado** - Concorrência, Performance, Arquitetura limpa  
✅ **MetaTrader 5 (MQL5)** - Expert Advisors e Sistemas de Copytrading  
✅ **DevOps & Cloud** - Automação com VPS, Deploy em produção  
✅ **Telegram Bot & Notificações** - Integração de bots para alertas em tempo real  

---

## 🗺️ Mapa dos Projetos

Os 11 projetos abaixo (mais este repositório) em uma tabela. Detalhes de arquitetura em [PROJECTS_DETAILS.md](PROJECTS_DETAILS.md).

| # | Projeto | Acesso | Stack | Última atividade | Em uma frase |
|--:|---------|:------:|-------|:----------------:|--------------|
| 1 | **Zeus MT5** | 🔒 | Python, MQL5, ONNX | out/2026 | EA de machine learning (LightGBM → ONNX) para XAUUSD com ciclo de retreino, validação e promoção |
| 2 | **Claude Trader em VPS** | 🔒 | Python, MQL5, PowerShell | out/2026 | Sistema autônomo 24/7: treino contínuo sobre cache de ticks, promoção determinística e execução mecânica |
| 3 | **Levain 2.0** | 🔒 | Python, FastAPI | jun/2026 | Plataforma de trading com ensemble de ML, múltiplas IAs e sistema de "champions" |
| 4 | **Levain** | 🔒 | Python | dez/2025 | Primeira geração: trading algorítmico com gestão de risco e análise de performance |
| 5 | **Metatrader5 EAS** | 🔒 | MQL5 | set/2026 | Código-fonte do Expert Advisor White Rabbit X |
| 6 | **White Rabbit X - Manual and Pre-Sets** | 🌍 | Python, MQL5 (sets), Markdown | set/2026 | 3.738 sets, manuais em 11 idiomas e o Autobot que os valida |
| 7 | **Historical Tool Manager MT5** | 🔒 | Python | ago/2026 | Histórico de preços para backtest no MT5 |
| 8 | **Copytrader MT5 - Multiple Terminal** | 🔒 | Python | fev/2026 | Replicação de operações entre vários terminais |
| 9 | **Copytrader MT5 - Dual Terminal** | 🔒 | Python | fev/2026 | Replicação de baixa latência entre dois terminais |
| 10 | **Big Guys Genius** | 🌍 | Python | out/2026 | 19 mesas de investimento e 9 sistemas independentes com book virtual |
| 11 | **corrmt5 (Correlation Via MT5)** | 🔒 | Python | out/2026 | Pairs trading por cointegração com execução protegida de duas pernas |
| - | **Portfolio Software Engineer** | 🌍 | Markdown | out/2026 | Este repositório |

🔒 privado (acesso por convite) · 🌍 público

---

## 🔒 Projetos Privados

> 💡 **Nota:** Repositórios privados podem ser acessados mediante convite. [Veja como solicitar acesso](#como-acessar-repositórios-privados)

### 1. **Levain** 
- **Status:** ✅ Estável (última atividade: dez/2025)
- **Linguagem:** Python
- **Descrição:** Sistema completo de trading algorítmico com gestão de risco avançada, histórico de operações e análise de performance. *Inclui notificações Telegram em tempo real.*
- **Skills:** `Python` `MetaTrader5` `Data Analysis` `Risk Management` `Telegram Bot` `Pandas` `NumPy`
- **Repositório:** `LucasPedroso96/Levain` (Privado)
- **License:** MIT

### 2. **Levain 2.0**
- **Status:** ⏸️ Última atividade de código: jun/2026
- **Linguagem:** Python
- **Descrição:** Plataforma híbrida de trading automatizado que combina análise técnica, ensemble de machine learning (XGBoost, LightGBM, CatBoost) e múltiplos provedores de IA (Claude, GPT-4, Gemini, Mistral e Ollama local), com dashboard web em FastAPI. Um sistema de **"champions"** promove estratégias por um pipeline de validação (walk-forward e Monte Carlo), a execução é orientada a eventos e os alertas saem por Telegram.
- **Skills:** `Python` `FastAPI` `Machine Learning` `Walk-Forward` `Multi-LLM` `Event-driven` `Unit Testing` `Telegram API`
- **Repositório:** `LucasPedroso96/Levain-2.0-` (Privado)
- **License:** MIT | **Criado:** Janeiro 2026

### 3. **Copytrader MT5 - Multiple Terminal**
- **Status:** ✅ Estável (última atividade: fev/2026)
- **Linguagem:** Python (template)
- **Descrição:** Sistema de copytrading que sincroniza múltiplos terminais MT5 com replicação automática de operações entre contas. *Notificações Telegram de operações.*
- **Skills:** `Python` `MetaTrader5 API` `Multi-threading` `Websockets` `Telegram Notifications` `Real-time Data`
- **Repositório:** `LucasPedroso96/Copytrader-Mt5-Multiple-Terminal` (Privado)

### 4. **Copytrader MT5 - Dual Terminal**
- **Status:** ✅ Estável (última atividade: fev/2026)
- **Linguagem:** Python
- **Descrição:** Versão simplificada do copytrader para sincronização entre dois terminais MT5 com baixa latência. *Com suporte a Telegram Bot.*
- **Skills:** `Python` `Real-time Sync` `Network Programming` `MetaTrader5` `Telegram Bot` `Concurrency`
- **Repositório:** `LucasPedroso96/Copytrader-Mt5-Dual-Terminal` (Privado)
- **Criado:** Janeiro 2026

### 5. **Claude Trader em VPS**
- **Status:** ✅ Ativo (rodando em VPS Windows; última atividade: out/2026)
- **Linguagem:** Python, MQL5, PowerShell
- **Descrição:** Sistema autônomo de trading 24/7 sobre 57 ativos de 6 classes. Um treinador contínuo varre um **cache local de ticks** (sem tocar a API ao vivo) e valida combinações de sinal com hold-out verdadeiro, Deflated Sharpe, consistência entre folds e selection-WFA. A promoção ao conjunto ativo é **determinística** (piso de score e orçamento de risco), a execução é **mecânica com o mesmo código do backtest** e o EA aplica saídas tick a tick. A IA (Claude) atua só numa camada administrativa **consultiva**: nunca aprova nem veta trade individual. Inclui rastreio de divergência entre ao vivo e backtest, sentinela com alertas Telegram, painel web e suíte de testes offline.
- **Skills:** `Python` `MQL5` `PowerShell` `Quant Validation` `Backtesting` `VPS Management` `Observability` `Telegram Alerts`
- **Repositório:** `LucasPedroso96/Claude-Trader-em-VPS` (Privado)
- **Criado:** Abril 2026

### 6. **Zeus MT5 - Claude EA**
- **Status:** 🚀 Ativo (desde ago/2026; última atividade: out/2026)
- **Linguagem:** Python, MQL5
- **Descrição:** Expert Advisor de machine learning para XAUUSD: as features são calculadas dentro do EA e um modelo **LightGBM exportado em ONNX** roda no MetaTrader 5, com paridade MQL5 ↔ Python verificada barra a barra. Um ciclo em Python retreina, valida (walk-forward purgado, triple-barrier, gates de promoção, hold-out contra o modelo titular) e promove o modelo ao vivo. Um segundo EA, multi-slot, opera vários pares modelo × sistema de gestão e mede cada um num livro virtual. Desenvolvido em duas máquinas sincronizadas por git, com painel web. A decisão de trade é do modelo; o Claude Code é ferramenta de desenvolvimento.
- **Skills:** `Python` `MQL5` `LightGBM` `ONNX` `Purged Walk-Forward` `Strategy Tester Automation` `Git Workflow`
- **Repositório:** `LucasPedroso96/ZeusMt5-ClaudeEA-` (Privado)
- **Criado:** Agosto 2026

### 7. **Metatrader5 EAS**
- **Status:** ✅ Ativo (última atividade: set/2026)
- **Linguagem:** MQL5
- **Descrição:** Código-fonte do **Expert Advisor White Rabbit X**: EA multi-indicador (11 motores de entrada mais Ichimoku) com mais de 10 sistemas de gestão de saída (SL/TP, trailing, breakeven, reversão, grid, martingale, D'Alembert, sinal puro), entrada pendente (Stop, Limit e OCO de rompimento), walk-forward interno, filtros de notícia, limite de perda diária e proteção global, e painel em 11 idiomas. Variantes Bollinger Bands e Candles Entry.
- **Skills:** `MQL5` `Algorithmic Trading` `Walk-Forward Optimization` `Order Management` `Risk Controls` `Performance Optimization`
- **Repositório:** `LucasPedroso96/Metatrader5EAS` (Privado)
- **License:** Boost 1.0 | **Criado:** Outubro 2023

### 8. **Historical Tool Manager MT5**
- **Status:** ✅ Ativo (última atividade: ago/2026)
- **Linguagem:** Python
- **Descrição:** Ferramenta para gerenciar e organizar dados históricos de preços para backtesting em MetaTrader5. Importa histórico real de tick e M1 como *Custom Symbols*, usado na etapa de confirmação por tick real do Autobot do White Rabbit X. Também disponível no [MQL5 Market](https://www.mql5.com/pt/market/product/188711).
- **Skills:** `Python` `Data Management` `File Organization` `MT5 Integration` `Automation`
- **Repositório:** `LucasPedroso96/Historical-Tool-Manager-MT5` (Privado)
- **License:** Other

### 9. **corrmt5 (Correlation Via MT5)** 🆕
- **Status:** 🧪 Novo (out/2026), em validação
- **Linguagem:** Python
- **Descrição:** Sistema de **pairs trading** (arbitragem estatística) para MetaTrader 5. Seleciona pares por correlação e cointegração (Engle-Granger, half-life e Hurst), gera sinais por z-score com hedge ratio travado, dimensiona por risco e aplica limites de portfólio com kill switch. A execução de duas pernas tem **proteção contra legging**: se a segunda perna falha, a primeira é desfeita. Reconcilia com a corretora, guarda estado em SQLite e roda o **mesmo código** em backtest walk-forward, paper trading e real. Conta real só opera com duas travas deliberadas. A validação com histórico H1 da corretora ainda não foi feita.
- **Skills:** `Python` `statsmodels` `Cointegration` `Pairs Trading` `Risk Management` `SQLite` `pytest`
- **Repositório:** `LucasPedroso96/Correlation-Via-MT5-` (Privado)
- **Testes:** mais de 75 offline | **Criado:** Outubro 2026

---

## 🌍 Projetos Públicos

### 1. **White Rabbit X - Manual and Pre-Sets**
- **Status:** ✅ Ativo (desde jul/2026; última atividade na `main`: set/2026)
- **Linguagem:** Python, sets do MQL5 e Markdown
- **Descrição:** Biblioteca pública de **3.738 sets de otimização** (89 ativos × 11 sistemas de gestão × variantes), manuais em **11 idiomas** e o **Autobot**: a automação em Python que gera, testa e valida cada set num circuito de 5 estágios (busca genética, refinamento, filtros de execução, confirmação por tick real e prova em % do saldo), com gate de Monte Carlo e de expectância em R. Inclui instalador, painel de campanha em FastAPI e cerca de 40 scripts de teste offline.
- **Skills:** `Python` `Backtesting` `Walk-Forward` `Monte Carlo` `Technical Writing` `i18n` `MT5 Automation`
- **📍 Link:** [github.com/LucasPedroso96/White-Rabbit-X-Manual-and-Pre-Sets](https://github.com/LucasPedroso96/White-Rabbit-X-Manual-and-Pre-Sets)
- **Wiki disponível:** ✅

### 2. **Big Guys Genius** 🆕
- **Status:** 🆕 Novo (out/2026)
- **Linguagem:** Python
- **Descrição:** 19 mesas de investimento (relatórios determinísticos de DCF, risco, análise técnica, sazonalidade com correção de múltiplos testes e outros) e 9 métodos de trade, cada um rodando como **sistema independente** (regras, risco e *magic number* próprios). O **book virtual** registra e mede os trades sobre preços reais do MT5 e, por construção, não consegue enviar uma ordem. O placar só conclui algo com 30 ou mais trades e mostra o resultado líquido do spread. Controles em passeio aleatório mostram que nenhum sistema "inventa" edge. Conta real exige duas travas. 288 testes.
- **Skills:** `Python` `pandas` `Quant Research` `Backtesting` `pytest` `ruff` `MT5 API`
- **📍 Link:** [github.com/LucasPedroso96/Big-Guys-Genius-](https://github.com/LucasPedroso96/Big-Guys-Genius-)
- **Aviso:** projeto educacional e experimental, não é recomendação de investimento. Os nomes de instituições e pessoas são *lentes* (métodos), sem qualquer relação com elas.

---

## 🎯 Produtos & Clientes em Produção

### White Rabbit X - Expert Advisor

**Plataforma:** MetaTrader 5 Marketplace  
**Status:** ✅ Ativo | ~50+ clientes ativos em produção  
**Linguagem:** MQL5  

#### 📊 Links & Referências

- **🔗 Produto:** [MQL5 Marketplace - White Rabbit X](https://www.mql5.com/pt/market/product/187173?source=Site+Profile#)
- **⭐ Perfil & Feedback:** [MQL5 - Lucas Siqueira Pedroso](https://www.mql5.com/pt/users/lucassiqueirape)
- **📈 Avaliações verificadas** de traders reais na plataforma

#### 💡 Destaques

✅ Clientes ativos com operações reais  
✅ Avaliações e feedback de produção  
✅ Suporte contínuo e atualizações  
✅ Biblioteca pública de 3.738 sets, manuais em 11 idiomas e automação de validação (Autobot)  
✅ EA na versão 1.24, com variantes Multi-Indicator, Bollinger Bands e Candles Entry  
✅ Versão 2.0+ em desenvolvimento baseada em demanda  

#### 🚀 Soft Launch - Early Adopters (2026)

**Programa Ativo:**
- ~12 clientes privados em fase de calibração
- Diversidade: Traders de proprietary firms, consultores independentes, gestores de carteira
- Feedback de produção validando novas features
- Roadmap priorizado por demanda real do mercado

*Clientes sob NDA - detalhes confidenciais não podem ser divulgados*

#### 🛠️ Skills Aplicadas

`Algorithmic Trading` `Risk Management` `Real-time Processing` `Performance Optimization` `User Support` `Product Iteration` `Market Validation`

### Historical Tool Manager - MQL5 Market

Importa histórico real de tick e M1 como *Custom Symbols* no MT5, para backtests em ativos que a corretora não cobre por tempo suficiente.

- **🔗 Produto:** [MQL5 Marketplace - Historical Tool Manager](https://www.mql5.com/pt/market/product/188711)

---

## 🧪 Engenharia de Validação e Segurança

Em trading algorítmico, o que separa um sistema de um acidente é a validação. Estas são as práticas que aplico, com o projeto onde cada uma está:

- **Paridade entre backtest e execução.** O Claude Trader avalia o sinal ao vivo com o mesmo código que o laboratório usou no backtest. O corrmt5 roda o mesmo motor em backtest, paper e real. O Big Guys Genius testa que o book virtual reproduz o backtest trade a trade.
- **Controles anti-overfit.** Hold-out verdadeiro (e lacrado, no Autobot), Deflated Sharpe, walk-forward purgado, Monte Carlo de drawdown e controles em passeio aleatório que provam que o código não inventa edge.
- **Segurança operacional.** Conta real só opera com duas travas deliberadas (Big Guys Genius e corrmt5), `order_check` antes de cada ordem, kill switch persistente, EA que falha fechado e uma regra dura: a IA nunca aprova nem veta trade individual (Claude Trader).
- **Testabilidade sem terminal.** O módulo do MT5 é injetável, então a lógica de execução roda em testes sem o terminal, que só existe no Windows. Mais de 460 testes offline nos três projetos mais recentes (Big Guys Genius 288, corrmt5 77, Claude Trader 100).
- **Auditoria cruzada entre projetos (out/2026).** Defeitos e proteções achados em um sistema foram portados para os outros: erro de fuso do servidor MT5 em consultas de histórico, fallback de modo de preenchimento de ordem, travas de conta real e suíte de testes que roda sem MT5.

---

## 🛠️ Stack de Tecnologias

### 💻 Linguagens de Programação

| Linguagem | Proficiência | Uso Principal |
|-----------|-------------|---------------|
| **Python** | ⭐⭐⭐⭐⭐ | Automação, APIs, Bots, Data Analysis |
| **MQL5** | ⭐⭐⭐⭐ | Expert Advisors, MetaTrader5 |
| **HTML/CSS** | ⭐⭐⭐ | Documentação, Interfaces |
| **C++** | ⭐⭐ | Otimizações específicas |

### 📦 Frameworks & Bibliotecas

```
✅ MetaTrader5 (Python API)      - Trading Platform Integration
✅ asyncio / threading           - Concorrência e Multi-threading
✅ WebSockets                    - Real-time Data Streaming
✅ Pandas / NumPy               - Data Analysis & Computation
✅ Flask / FastAPI              - Web Frameworks (quando necessário)
✅ Requests                     - HTTP Client
✅ APScheduler                  - Task Scheduling
✅ SQLAlchemy                   - ORM Database
✅ python-telegram-bot          - Telegram Bot Integration
✅ LightGBM / XGBoost / CatBoost - ML tabular para classificação de sinais
✅ ONNX / ONNX Runtime          - Modelos treinados em Python executando dentro do MQL5
✅ PyTorch                      - LSTM (famílias de modelo com memória)
✅ scikit-learn / statsmodels   - Validação, cointegração (Engle-Granger), estatística
✅ Optuna                       - Otimização de hiperparâmetros
✅ Numba                        - Aceleração de simulação por tick
✅ pytest / ruff                - Testes e lint
✅ SQLite                       - Estado e reconciliação (corrmt5)
```

### 🚀 Ferramentas & Plataformas

- **MetaTrader 5** - Plataforma principal de trading
- **Telegram Bot API** - Integração de bots e notificações
- **VPS (Linux/Windows)** - Execução 24/7 de bots
- **GitHub** - Versionamento e colaboração
- **Docker** - Containerização
- **Git** - Controle de versão
- **PowerShell / Agendador de Tarefas (Windows)** - Orquestração dos serviços em VPS
- **Strategy Tester do MT5 automatizado** - Campanhas de otimização e validação
- **Claude AI API** - Integração de LLM

### 🎯 Conceitos & Padrões Aplicados

```
Trading & Finance:
  ✅ Algorithmic Trading Strategies
  ✅ Risk Management & Position Sizing
  ✅ Backtesting & Performance Analysis
  ✅ Real-time Order Management
  ✅ Market Data Processing

Machine Learning & Validação Quantitativa:
  ✅ Walk-forward purgado e hold-out lacrado
  ✅ Triple-barrier labeling
  ✅ Deflated Sharpe Ratio e Monte Carlo de drawdown
  ✅ Paridade backtest ↔ execução (mesmo código)
  ✅ Exportação de modelos para ONNX com verificação de paridade MQL5 ↔ Python
  ✅ Cointegração e pairs trading

Integração & Notificações:
  ✅ Telegram Bot Integration
  ✅ Real-time Notifications
  ✅ Webhook Management
  ✅ Message Queue Systems

Software Engineering:
  ✅ Clean Code Architecture
  ✅ SOLID Principles
  ✅ Design Patterns (Singleton, Observer, Factory)
  ✅ API Design & RESTful Principles
  ✅ Error Handling & Logging
  ✅ Unit Testing & Integration Testing
  ✅ Documentation & Code Comments

Infrastructure:
  ✅ Multi-threading / Concurrency
  ✅ Real-time Data Processing
  ✅ VPS Management & Automation
  ✅ Database Design & Optimization
  ✅ DevOps Practices
```

---

## 🔐 Como Acessar Repositórios Privados

Caso você seja um **recrutador, contratante ou membro da comunidade** interessado em explorar meus projetos privados:

### ✅ Opção 1: Convite de Colaborador (Recomendado)

1. Abra uma **[Issue](https://github.com/LucasPedroso96/Portfolio-Software-Engineer/issues/new)** neste repositório solicitando acesso
2. Inclua as informações:
   - Seu usuário GitHub
   - Empresa/Contexto
   - Qual(is) projeto(s) te interessa(m)
   - Motivo do acesso

**Template de Issue:**
```markdown
**Título:** Solicitar acesso a repositório privado

**Descrição:**
- **Usuário GitHub:** @seu-usuario
- **Empresa/Contexto:** XYZ Company (Recrutador/Parceria)
- **Projeto(s) de interesse:** Levain 2.0, Copytrader MT5
- **Motivo:** Avaliação de candidato para vaga Senior Python Developer
```

3. Você será adicionado como **Collaborator** ao repositório privado em até 24h

### 📧 Opção 2: Contato Direto
- **LinkedIn:** [Lucas Pedroso](https://www.linkedin.com/in/lucas-pedroso-96)
- **GitHub Issues:** [Abra uma issue neste repo](https://github.com/LucasPedroso96/Portfolio-Software-Engineer/issues)

### 📥 Opção 3: Download Privado
- Solicite um arquivo ZIP/TAR do repositório
- Compartilhamento seguro

---

## 🤝 Contribuições & Colaboradores

### 🎯 Procuramos por Colaboradores!

Se você é um **desenvolvedor Python, trader ou entusiasta** interessado em:

- 🤖 Melhorar sistemas de trading algorítmico
- ⚡ Otimizar performance de bots
- 📊 Adicionar novas estratégias de trading
- 📱 Integração de Telegram Bot e notificações
- 🔍 Code reviews e sugestões
- 📚 Melhorar documentação
- 🧪 Escrever testes e CI/CD

**Como contribuir:**

1. ⭐ **Star** este repositório
2. 📌 **Fork** e crie uma branch (`git checkout -b feature/minha-feature`)
3. 💬 **Abra uma Issue** com suas ideias
4. 🔗 **Envie um Pull Request** com suas contribuições
5. 📞 **Conecte via LinkedIn** para discussões maiores

**Áreas de interesse para colaboração:**
- [ ] Refatoração de código legado
- [ ] Novos indicadores técnicos
- [ ] Estratégias de hedging
- [ ] Melhorias de performance
- [ ] Testes automatizados
- [ ] Documentação técnica
- [ ] Expansão de Telegram Bot features

---

## 📊 Estatísticas do Portfólio

| Métrica | Valor |
|---------|-------|
| **Projetos** | 11 (mais este repositório de portfólio) |
| **Repositórios Privados** | 9 |
| **Repositórios Públicos** | 2 (White Rabbit X Manual and Pre-Sets e Big Guys Genius) |
| **Linguagens Principais** | Python, MQL5 (e PowerShell, HTML/JS nos painéis) |
| **Integrações Principais** | MetaTrader5, ONNX, Telegram Bot, Claude AI (consultivo) |
| **Testes automatizados** | Mais de 460 offline em Big Guys Genius, corrmt5 e Claude Trader |
| **Atividade recente** | Semana de 26/09 a 02/10/2026: 150 commits e cerca de 46 mil linhas líquidas escritas à mão (código e documentação, sem arquivos gerados), em 7 repositórios, com apoio do Claude Code |
| **Última Atualização** | Outubro 3, 2026 |

---

## 🎓 Como Usar Este Portfólio

### 👔 Para Recrutadores & Empresas:
1. Explore a lista completa de projetos acima
2. Veja links dos produtos em produção com clientes reais
3. Solicite acesso aos repositórios privados que interessam ([abra uma Issue](#como-acessar-repositórios-privados))
4. Avalie código, arquitetura, padrões e práticas
5. Entre em contato para discussão técnica

### 👨‍💻 Para Colaboradores & Desenvolvedores:
1. Explore os repositórios públicos
2. Abra **Issues** com sugestões, bugs ou melhorias
3. Envie **Pull Requests** com suas contribuições
4. Participe das **Discussions** técnicas
5. Faça um fork e contribua!

### 📚 Para Aprender:
1. Estude os padrões de código e arquitetura
2. Veja práticas em Python, APIs e MetaTrader5
3. Acompanhe evolução dos projetos (commits e histórico)
4. Leia a documentação técnica
5. Entenda conceitos de trading algorítmico e integração de bots

---

## 💼 Experiência & Certificações

- ✅ **Trading Algorítmico** - 3+ anos
- ✅ **Python Avançado** - 4+ anos
- ✅ **APIs & Integração** - 3+ anos
- ✅ **Telegram Bot Development** - 2+ anos
- ✅ **MetaTrader5 (MQL5)** - 2+ anos
- ✅ **DevOps & VPS** - 2+ anos

---

## 📞 Contato & Redes

- **GitHub:** [@LucasPedroso96](https://github.com/LucasPedroso96)
- **LinkedIn:** [Lucas Pedroso](https://www.linkedin.com/in/lucas-pedroso-96)
- **MQL5 Profile:** [Lucas Siqueira Pedroso](https://www.mql5.com/pt/users/lucassiqueirape)
- **Issues:** [Abra uma Issue aqui](https://github.com/LucasPedroso96/Portfolio-Software-Engineer/issues)

---

## 📄 Licenças

Cada repositório possui sua própria licença:
- 🔵 **MIT License** - Levain, Levain 2.0
- 🔴 **Boost Software License 1.0** - Metatrader5EAS
- ⚫ **Other** - Historical Tool Manager MT5
- 🟢 **Sem licença definida** - Demais repositórios (consultar para uso comercial)

---

## 🚀 Roadmap Futuro

- [ ] Versão 3.0 do Levain com Machine Learning
- [ ] Integração com mais brokers (não só MT5)
- [x] Dashboard web em tempo real (entregue no Claude Trader, Zeus, Big Guys Genius e no painel de campanha do Autobot)
- [ ] Mobile app para monitoramento
- [ ] Expansão de Telegram Bot features (comandos avançados, gráficos)
- [ ] Documentação em Inglês (os manuais do White Rabbit X já existem em 11 idiomas)
- [ ] Validar o corrmt5 com histórico H1 da corretora antes de qualquer ordem
- [ ] Rodar o book virtual do Big Guys Genius por meses sobre preços reais do MT5
- [ ] Integrar o motor de simulação por tick em Python (em desenvolvimento) ao circuito do Autobot
- [ ] Publicação de artigos técnicos
- [ ] Community Discord/Slack
- [ ] White Rabbit X versão premium

---

## ⭐ Suporte

Se este portfólio foi útil:
- 🌟 Deixe uma **Star** neste repositório!
- 📢 Compartilhe com amigos desenvolvedores
- 💬 Abra issues com feedback
- 🤝 Considere colaborar!

---

<div align="center">

**Desenvolvido com ❤️ por [Lucas Pedroso](https://github.com/LucasPedroso96)**

Última atualização: **Outubro 3, 2026**

[⬆ Voltar ao topo](#-software-engineer-portfolio)

</div>
