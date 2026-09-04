# 📚 Detalhes Técnicos dos Projetos

Documentação aprofundada sobre a arquitetura, tecnologias e decisões técnicas de cada projeto.

## 📋 Sumário

- [Projetos Privados](#projetos-privados)
- [Projetos Públicos](#projetos-públicos)
- [Arquitetura Comum](#arquitetura-comum)

---

## 🔒 Projetos Privados

### 1. Levain & Levain 2.0

**Descrição:** Sistema de trading algorítmico completo com gestão de risco avançada.

**Arquitetura:**
```
Levain/
├── core/
│   ├── trading_engine.py      # Motor de execução
│   ├── risk_manager.py        # Gestão de risco
│   └── order_handler.py       # Processamento de ordens
├── strategies/
│   ├── base_strategy.py       # Classe base
│   ├── momentum.py            # Estratégia momentum
│   └── mean_reversion.py      # Estratégia mean reversion
├── data/
│   ├── market_data.py         # Coleta de dados
│   └── indicators.py          # Indicadores técnicos
├── utils/
│   ├── logger.py              # Logging
│   └── config.py              # Configurações
└── tests/
    └── test_*.py              # Testes unitários
```

**Tecnologias:**
- Python 3.9+
- MetaTrader5 API
- Pandas / NumPy
- SQLite (histórico)
- APScheduler (agendamento)

**Features Principais:**
- ✅ Multi-strategy support
- ✅ Risk management automático
- ✅ Backtesting engine
- ✅ Real-time order execution
- ✅ Performance analytics

**Como Acessar:** [Solicitar acesso via Issue](https://github.com/LucasPedroso96/Portfolio-Software-Engineer/issues)

---

### 2. Copytrader MT5 (Dual & Multiple Terminal)

**Descrição:** Sistema de replicação de operações entre múltiplos terminais MT5.

**Arquitetura:**
```
Copytrader/
├── master_account/
│   ├── order_listener.py      # Monitora ordens
│   └── signal_generator.py    # Gera sinais
├── slave_accounts/
│   ├── order_replicator.py    # Replica ordens
│   └── risk_adjuster.py       # Ajusta tamanho
├── sync/
│   ├── websocket_client.py    # Comunicação
│   └── order_sync.py          # Sincronização
├── config/
│   └── account_mappings.json  # Configuração de contas
└── tests/
    └── test_*.py
```

**Tecnologias:**
- Python 3.8+
- WebSockets
- Threading/Asyncio
- MetaTrader5 API
- JSON (configuração)

**Features:**
- ✅ Sincronização em tempo real
- ✅ Ajuste automático de tamanho
- ✅ Failover automático
- ✅ Logging detalhado
- ✅ Suporte multi-conta

**Performance:**
- Latência: < 100ms
- Taxa de sucesso: > 99.8%

---

### 3. Claude Trader em VPS & Zeus MT5

**Descrição:** Bots de trading integrados com Claude AI para análise inteligente.

**Arquitetura:**
```
ClaudeTrader/
├── ai_integration/
│   ├── claude_client.py       # Cliente Claude API
│   ├── prompt_engine.py       # Templates de prompts
│   └── response_parser.py     # Parse de respostas
├── trading/
│   ├── mt5_interface.py       # Interface MT5
│   └── execution.py           # Execução de trades
├── analysis/
│   ├── market_analyzer.py     # Análise de mercado
│   └── signal_processor.py    # Processamento de sinais
└── vps_management/
    ├── auto_restart.py        # Auto-restart
    └── monitoring.py          # Monitoramento
```

**Tecnologias:**
- Python 3.10+
- Claude API (anthropic-sdk)
- MetaTrader5
- APScheduler
- Logging estruturado

**Features:**
- ✅ Análise de mercado por IA
- ✅ Recomendações inteligentes
- ✅ Execução automática
- ✅ 24/7 VPS operation
- ✅ Monitoramento remoto

---

### 4. Metatrader5 EAS

**Descrição:** Coleção de Expert Advisors profissionais em MQL5.

**Componentes:**
- Scalper EA - Operações rápidas
- Swing Trader EA - Operações de curto prazo
- Grid EA - Estratégia de grid
- Hedge EA - Estratégia de cobertura

**Tecnologias:**
- MQL5
- OnTick/OnStart event handlers
- Trade API (MT5)
- Object-Oriented MQL5

**Performance:**
- Drawdown máximo: 15-20%
- Win rate: 55-65%
- Profit factor: 1.5-2.0

---

### 5. Historical Tool Manager MT5

**Descrição:** Ferramenta de gestão de dados históricos para backtesting.

**Funcionalidades:**
- Download automático de histórico
- Validação de dados
- Formatação padrão
- Organização por período
- Limpeza de duplicatas

**Tecnologias:**
- Python 3.8+
- MetaTrader5
- Pandas
- SQLite

---

## 🌍 Projetos Públicos

### 1. Organização AlgoMT5

**Link:** https://github.com/LucasPedroso96/Organiza-o-AlgoMT5-Parceria-com-a-Gangue

**Descrição:** Projeto colaborativo com foco em desenvolvimento de algoritmos.

**Status:** Aberto para contribuições!

---

### 2. White Rabbit X - Manual

**Link:** https://github.com/LucasPedroso96/White-Rabbit-X-Manual-and-Pre-Sets

**Descrição:** Documentação completa e presets do sistema White Rabbit X.

**Conteúdo:**
- 📖 Manual detalhado
- ⚙️ Presets otimizados
- 🎥 Tutoriais
- 💡 Best practices

**Status:** Aberto para contribuições!

---

## 🏗️ Arquitetura Comum

### Padrões Aplicados

#### 1. Strategy Pattern
```python
class BaseStrategy:
    def analyze(self, data):
        pass
    
    def generate_signal(self):
        pass

class MomentumStrategy(BaseStrategy):
    def analyze(self, data):
        # Implementação específica
        pass
```

#### 2. Observer Pattern
```python
class OrderListener:
    def on_order_created(self, order):
        pass
    
    def on_order_closed(self, order):
        pass

class OrderManager:
    def __init__(self):
        self.listeners = []
    
    def add_listener(self, listener):
        self.listeners.append(listener)
```

#### 3. Factory Pattern
```python
class StrategyFactory:
    @staticmethod
    def create_strategy(strategy_type: str) -> BaseStrategy:
        if strategy_type == 'momentum':
            return MomentumStrategy()
        elif strategy_type == 'mean_reversion':
            return MeanReversionStrategy()
```

### Error Handling

```python
class TradingException(Exception):
    pass

class InsufficientFundsException(TradingException):
    pass

class OrderExecutionException(TradingException):
    pass

try:
    bot.execute_trade()
except InsufficientFundsException:
    logger.error("Não há fundos suficientes")
except OrderExecutionException:
    logger.error("Erro ao executar ordem")
```

### Logging

```python
import logging

logger = logging.getLogger(__name__)

logger.debug("Debug info")
logger.info("Order executed successfully")
logger.warning("High drawdown detected")
logger.error("Connection lost")
logger.critical("System shutdown")
```

### Configuration Management

```python
# config.py
import json

class Config:
    def __init__(self, config_file: str):
        with open(config_file) as f:
            self.data = json.load(f)
    
    def get(self, key: str, default=None):
        return self.data.get(key, default)

# Uso
config = Config('config.json')
max_leverage = config.get('max_leverage', 50)
```

---

## 🔐 Segurança

### Boas Práticas Implementadas

- ✅ Credenciais em variáveis de ambiente
- ✅ Validação de entrada
- ✅ Logs de auditoria
- ✅ Encriptação de dados sensíveis
- ✅ Rate limiting
- ✅ Retry logic com backoff

---

## 📊 Performance & Optimization

### Técnicas Aplicadas

- ✅ Caching de dados
- ✅ Connection pooling
- ✅ Async/await para I/O
- ✅ Batch processing
- ✅ Índices de banco de dados

---

## 🧪 Testing Strategy

```python
# Unit Tests
def test_risk_calculation():
    bot = TradingBot(balance=10000)
    risk = bot.calculate_risk(2.0)
    assert risk == 200.0

# Integration Tests
def test_order_execution():
    bot = TradingBot()
    order = bot.execute_trade('BUY', 1.0)
    assert order.status == 'EXECUTED'

# Performance Tests
def test_order_latency():
    import time
    start = time.time()
    bot.execute_trade('BUY', 1.0)
    latency = (time.time() - start) * 1000
    assert latency < 100  # < 100ms
```

---

Última atualização: Setembro 4, 2026
