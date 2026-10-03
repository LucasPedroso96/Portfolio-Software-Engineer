# 📚 Detalhes Técnicos dos Projetos

Arquitetura, tecnologias e decisões técnicas de cada projeto. Tudo aqui descreve o que existe nos repositórios; os números são contagens de arquivos, testes e componentes, nunca promessas de desempenho. Para o panorama geral, veja o [README](README.md).

## 📋 Sumário

- [Projetos Privados](#-projetos-privados)
- [Projetos Públicos](#-projetos-públicos)
- [Padrões de Engenharia Comuns](#-padrões-de-engenharia-comuns)

---

## 🔒 Projetos Privados

### 1. Claude Trader em VPS

**Descrição:** Sistema autônomo de trading 24/7 em VPS Windows, sobre 57 ativos de 6 classes (forex, metais, índices, energia, cripto, ações).

**Fluxo:**
```
cache de ticks (data_lake) ──► edge_trainer (24/7, prioridade baixa) ──► playbook de combos validados
                                                                              │
edge_tracker (live × backtest) ◄── auto_executor (mecânico) ◄── promote.py (score + orçamento de risco)
                                          │
                                       ClaudeEA.mq5 (saídas tick a tick)
```

**Estrutura:**
```
python/
├── data_lake.py        # Cache de ticks por mês (.npz): o treino nunca toca a API ao vivo
├── signal_lab.py       # Laboratório: hold-out verdadeiro, Deflated Sharpe, selection-WFA, Monte Carlo
├── tick_engine.py      # Simulação por tick (versão Numba para o laço quente)
├── edge_trainer.py     # Daemon de treino contínuo
├── promote.py          # Promoção determinística: piso de score + orçamento de risco
├── auto_executor.py    # Execução mecânica, mesmo código de sinal do backtest
├── exit_engine.py      # Fallback de saídas para posições sem cache no EA
├── edge_tracker.py     # Divergência entre resultado ao vivo e backtest (teste binomial)
├── policy.py           # "Dials" do dono em JSON, lidos a cada ciclo
├── sentinel_watch.py   # Vigilância e alertas Telegram
├── dashboard.py        # Painel web
└── tests/              # Suíte unittest offline
automation/             # Tarefas agendadas em PowerShell
ClaudeEA.mq5            # Expert Advisor
trainer_node/           # Treino em uma segunda máquina
```

**Tecnologias:** Python 3.11, MetaTrader5, pandas, NumPy, Numba, MQL5, PowerShell, Agendador de Tarefas do Windows, Telegram Bot API.

**Decisões de projeto:**
- ✅ A IA (Claude) é uma camada **consultiva** que analisa o conjunto de algoritmos; nunca aprova nem veta trade individual, e falha aberta (sem ela, o determinístico segue).
- ✅ Hard gates contra overfit (DSR, consistência entre folds, expectância mínima) e *advisories* que só ranqueiam.
- ✅ Arquivos de estado escritos de forma atômica (arquivo temporário e `os.replace`).
- ✅ Dials de política lidos frescos a cada ciclo: mudar um limite não exige reinício nem commit.

---

### 2. Zeus MT5 - Claude EA

**Descrição:** Expert Advisor de machine learning para XAUUSD (M15) com um ciclo Python que retreina, valida e promove o modelo ao vivo. Desenvolvido em duas máquinas sincronizadas por git.

**Estrutura:**
```
mql5/
├── Experts/Zeus/        # Zeus.mq5 (EA de modelo único) e ZeusRegente.mq5 (EA multi-slot)
└── Include/Zeus/        # Features, ONNX, risco, livro virtual, conta, log
python/zeus/             # data → features → labeling (triple-barrier) → cv (walk-forward purgado)
                         #   → train (LightGBM) → export_onnx → backtest → gate → deploy
python/tools/            # Auditorias, pesquisas e testes de regressão
autobot/                 # Campanha, triagem, hold-out, gate ao vivo, roster, livro virtual, painel
scripts/                 # Vigias e tarefas agendadas (PowerShell)
status/                  # Retrato de cada máquina, sincronizado por git
```

**Tecnologias:** Python, MQL5, LightGBM, XGBoost, CatBoost, scikit-learn, PyTorch (LSTM), ONNX / ONNX Runtime, pandas / pyarrow, FastAPI, Strategy Tester do MT5 automatizado.

**Decisões de projeto:**
- ✅ **Paridade MQL5 ↔ Python**: ferramentas conferem que features e inferência batem barra a barra antes de qualquer promoção.
- ✅ Uma feature foi **removida** porque divergia entre o EA ao vivo e o Python (o tester sintetiza o volume de ticks): melhor perder sinal do que depender de algo que só funciona ao vivo.
- ✅ Subida ao live por camadas: modelo limpo (sem vazamento de seleção), score acima do sistema puro e **hold-out** contra o titular.
- ✅ O terminal ao vivo nunca é automatizado por script: tudo que mexe no MT5 vai para um terminal separado ("gym"), com travas de código que recusam o real.
- ✅ Um único componente commita automaticamente (o transporte de status entre as duas máquinas), e só quando o retrato muda de verdade.

---

### 3. Levain 2.0

**Descrição:** Plataforma de trading automatizado com análise técnica, ensemble de ML e múltiplos provedores de IA, servida por um dashboard FastAPI.

**Estrutura (resumida):**
```
main.py                  # Aplicação FastAPI
src/
├── ai/, integrations/   # Claude, GPT-4, Gemini, Mistral, Ollama
├── ml/, optimization/   # XGBoost, LightGBM, CatBoost, Optuna
├── backtesting/, risk/  # Backtest e gestão de risco
├── mt5/, indicators/    # MetaTrader5 e indicadores
├── notifications/       # Telegram
└── dashboard/, api/     # Interface web
scripts/champions/       # Sistema de "champions": pipeline de promoção de estratégias
tests/                   # unit, integration, e2e, verification
```

**Tecnologias:** Python 3.11+, FastAPI, XGBoost / LightGBM / CatBoost, Optuna, Numba, MetaTrader5, SQLite, Telegram.

**Decisões de projeto:**
- ✅ Execução **orientada a eventos**: monitores reagem ao tick em vez de varrer em laço.
- ✅ Promoção de estratégias por pipeline de validação (walk-forward e Monte Carlo), com auditorias documentadas dos defeitos encontrados.
- ✅ Credenciais fora do repositório e `.env` gerido pelo dashboard.

---

### 4. Metatrader5 EAS

**Descrição:** Código-fonte do Expert Advisor **White Rabbit X**.

**Estrutura:**
```
White Rabbit/
├── EA/          # Global Multi-Indicator (canônico), Bollinger Bands, Candles Entry, versão PT-BR
├── Include/     # Perda diária, proteção global, filtro de notícias
├── Scripts/     # Exportador de notícias e autoteste dos filtros
├── Sets/        # Biblioteca de sets de otimização
├── Docs/        # Manual de sets, otimização e WFO
├── Manuals/     # 11 idiomas
├── Market/      # Descrições do produto
└── AutoBotSetup # Instalador
```

**Tecnologias:** MQL5 (cada EA tem cerca de 10 mil linhas), walk-forward interno, painel de gráfico em 11 idiomas.

**Funcionalidades do EA (v1.24):**
- ✅ 11 motores de entrada selecionáveis mais Ichimoku
- ✅ Mais de 10 sistemas de gestão de saída: SL/TP, trailing, breakeven, reversão, grid, martingale, D'Alembert, sinal puro, grid inverso e OCO de rompimento
- ✅ Entrada pendente (Stop, Limit e OCO)
- ✅ Limites de perda diária e proteção global; filtro de notícias

---

### 5. corrmt5 (Correlation Via MT5)

**Descrição:** Sistema de pairs trading por cointegração com execução no MetaTrader 5.

**Estrutura:**
```
src/corrmt5/
├── stats.py, selection.py   # OLS, Engle-Granger, half-life, Hurst, escolha gulosa e diversificada
├── strategy.py, sizing.py   # Sinais por z-score, tamanho por risco
├── risk.py                  # Limites de portfólio, exposição por moeda, kill switch
├── execution.py             # Duas pernas com proteção contra legging
├── engine.py, state.py      # Orquestração, reconciliação e SQLite
├── broker/                  # mt5 (real), paper, sim (backtest), ledger
└── backtest.py, data.py     # Walk-forward; CSV/Parquet de qualquer layout
```

**Tecnologias:** Python 3.10+, statsmodels, pandas, NumPy, SQLite, pytest.

**Decisões de projeto:**
- ✅ A interface `Broker` permite rodar **o mesmo código** em backtest, paper e real.
- ✅ Perna mais cara primeiro; se a segunda falha, a primeira é desfeita.
- ✅ Chaves desconhecidas no YAML geram erro (protege contra erro de digitação).
- ✅ Conta real só abre posição com duas travas; fechar posição nunca é bloqueado.
- ✅ Estado: o projeto está em validação. Os testes com dados sintéticos validam o software, não o resultado.

---

### 6. Copytrader MT5 (Dual e Multiple Terminal)

**Descrição:** Replicação automática de operações entre terminais MT5 (dois terminais com baixa latência, ou vários terminais).

**Tecnologias:** Python, API do MetaTrader5, WebSockets, threading / asyncio, notificações Telegram.

*Detalhes de arquitetura sob consulta (repositórios privados).*

---

### 7. Levain

**Descrição:** Primeira geração do sistema de trading algorítmico, com gestão de risco, histórico de operações e análise de performance.

**Tecnologias:** Python, MetaTrader5, pandas, NumPy, Telegram.

*Detalhes de arquitetura sob consulta (repositório privado).*

---

### 8. Historical Tool Manager MT5

**Descrição:** Gestão de dados históricos de preços para backtesting. Importa histórico real de tick e M1 como Custom Symbols no MT5 (também publicado no [MQL5 Market](https://www.mql5.com/pt/market/product/188711)).

**Tecnologias:** Python, MetaTrader5, pandas.

*Detalhes de arquitetura sob consulta (repositório privado).*

---

## 🌍 Projetos Públicos

### 1. White Rabbit X - Manual and Pre-Sets

**Link:** https://github.com/LucasPedroso96/White-Rabbit-X-Manual-and-Pre-Sets

**Descrição:** Biblioteca de sets, manuais e o Autobot que os gera e valida.

**Estrutura:**
```
Sets/<classe>/<ATIVO>/<NN_SISTEMA>/<LADO>_<VARIANTE>.set   # 3.738 sets
Manuals/<idioma>/                                           # 11 idiomas em .md, .pdf e .docx
Autobot/                                                    # Automação em Python
├── campanha.py, optimize_two_stage.py                      # Circuito de 5 estágios
├── monte_carlo_wrx.py, wfo_matrix.py                       # Gate de Monte Carlo e matriz de janelas IS/OOS
├── preflight.py                                            # Semáforo antes de uma campanha
├── testar_pendentes.py, testar_sistemas.py                 # Matrizes de teste no Strategy Tester
└── dashboard_campanha.py                                   # Painel de controle (FastAPI)
AutoBotSetup/                                               # Instalador
```

**Circuito de validação de cada set:** busca genética → busca refinada → filtros de execução → **confirmação por tick real** → prova em % do saldo, com gate de Monte Carlo (drawdown) e de expectância em R fora da amostra.

**Decisões de projeto:**
- ✅ Medir em **tick real**: no modo OHLC de 1 minuto, perdas de trailing e grid aparecem muito menores do que são.
- ✅ Otimizar em Fixed-R (comparável entre ativos) e entregar também com sizing em % do saldo.
- ✅ Cerca de 40 scripts de teste offline que checam o gerador, o ledger e as regras de decisão.

**Status:** Aberto para contribuições!

---

### 2. Big Guys Genius

**Link:** https://github.com/LucasPedroso96/Big-Guys-Genius-

**Descrição:** 19 mesas de investimento e 9 sistemas de trade independentes, com book virtual sobre preços reais do MT5.

**Estrutura:**
```
src/bgg/
├── library/    # Os 19 prompts, com front matter
├── desks/      # Uma mesa por arquivo: relatório determinístico e voto
├── systems/    # Sistemas independentes (técnicos, tendência, quant, valor)
├── brokers/    # base, mt5 (real), paper, virtual (book virtual), feeds
├── risk.py     # Dimensionamento, teto de calor da conta, kill switch persistente
├── metrics.py  # R-múltiplo, t-stat, placar honesto
├── preflight.py# `bgg mt5-check`: diagnóstico somente leitura do primeiro contato com o MT5
└── cli.py      # Comando `bgg`
```

**Tecnologias:** Python 3.10+, pandas, NumPy, SciPy, PyYAML, pytest, ruff (288 testes).

**Decisões de projeto:**
- ✅ O book virtual enxerga a fonte só por um `PriceFeed` de leitura: não consegue enviar ordem, por construção, e há teste para isso.
- ✅ Controle em passeio aleatório: nenhum sistema produz edge onde não há edge.
- ✅ Risco com teto absoluto por trade, calor da conta somado entre sistemas e conta real só com duas travas.

**Aviso:** projeto educacional e experimental, não é recomendação de investimento.

---

### 3. Organização AlgoMT5

**Link:** https://github.com/LucasPedroso96/Organiza-o-AlgoMT5-Parceria-com-a-Gangue

**Descrição:** Projeto colaborativo com foco em desenvolvimento de algoritmos.

**Status:** Aberto para contribuições!

---

## 🏗️ Padrões de Engenharia Comuns

Padrões que aparecem de fato em mais de um projeto.

### Módulo do MT5 injetável

O pacote `MetaTrader5` só existe no Windows. Os adaptadores recebem o módulo como parâmetro, e os testes passam um módulo falso:

```python
broker = MT5Broker(MT5Config(login=123, password="pw", server="Srv"), mt5_module=FakeMT5())
```

### Escrita atômica de estado

Arquivos que outro processo lê (EA, painel, vigias) são gravados em um arquivo temporário e trocados com `os.replace`, para ninguém ler um arquivo pela metade.

### Reserva atômica entre processos

Instâncias paralelas da busca de modelos disputam pares reservando-os com um arquivo criado de forma exclusiva (`O_CREAT | O_EXCL`), com reserva de processo morto ou velha sendo refeita.

### Hard gate × advisory

Cada critério de validação é explicitamente um **gate duro** (reprova) ou um **advisory** (só reporta e ranqueia), e a política que os liga ou desliga fica num arquivo de configuração.

### Falhar do lado seguro

O EA falha fechado (sem aprovação válida, nenhuma ordem), a camada de IA falha aberta (sem ela, o sistema determinístico segue) e a trava de conta real exige um ato deliberado.

### Paridade como teste

Onde há duas implementações da mesma lógica (MQL5 e Python, backtest e execução, book virtual e backtest), existe uma ferramenta ou um teste automático que as compara.

---

Última atualização: Outubro 3, 2026
