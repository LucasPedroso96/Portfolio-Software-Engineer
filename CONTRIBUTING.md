# 🤝 Guia de Contribuição

Obrigado por considerar contribuir para meus projetos! Este documento fornece diretrizes para fazer isso de forma eficaz.

## 📋 Índice

- [Código de Conduta](#código-de-conduta)
- [Como Começar](#como-começar)
- [Processo de Contribuição](#processo-de-contribuição)
- [Diretrizes de Commit](#diretrizes-de-commit)
- [Pull Request](#pull-request)
- [Reporte de Bugs](#reporte-de-bugs)
- [Solicitação de Features](#solicitação-de-features)

---

## 📜 Código de Conduta

Esperamos que todos os colaboradores:

- ✅ Sejam respeitosos com outras pessoas
- ✅ Forneçam feedback construtivo
- ✅ Focarem no código e ideias, não em pessoas
- ✅ Sigam as melhores práticas de desenvolvimento

---

## 🚀 Como Começar

### 1. Fork o Repositório
```bash
git clone https://github.com/seu-usuario/Portfolio-Software-Engineer.git
cd Portfolio-Software-Engineer
```

### 2. Crie uma Branch
```bash
git checkout -b feature/sua-feature
# ou
git checkout -b fix/seu-bug
```

### 3. Configure o Ambiente
```bash
# Python
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

pip install -r requirements.txt
```

### 4. Faça suas Mudanças
- Escreva código limpo
- Adicione testes
- Documente suas mudanças

### 5. Teste Tudo
```bash
pytest tests/
python -m flake8 src/
```

---

## 🔄 Processo de Contribuição

### Passo 1: Identifique um Problema
- Procure por issues marcadas com `good first issue`
- Ou abra uma nova issue para discutir sua ideia

### Passo 2: Discuta Grandes Mudanças
Para mudanças significativas:
1. Abra uma **Issue** descrevendo a mudança
2. Aguarde feedback dos mantenedores
3. Após aprovação, implemente

### Passo 3: Implemente
```bash
git checkout -b feature/minha-contribuicao
# ... código ...
git add .
git commit -m "Add: descrição clara da feature"
```

### Passo 4: Envie um Pull Request
```bash
git push origin feature/minha-contribuicao
```

---

## 💬 Diretrizes de Commit

Use a convenção **Conventional Commits**:

```
type(scope): descrição curta

Descrição mais detalhada se necessário.
```

### Tipos Permitidos:
- `feat:` - Nova feature
- `fix:` - Correção de bug
- `docs:` - Documentação
- `style:` - Formatação de código
- `refactor:` - Refatoração sem mudança funcional
- `test:` - Adição de testes
- `chore:` - Tarefas de build, dependências

### Exemplos:
```
feat(copytrader): add multi-terminal sync
fix(levain): handle null order prices
docs(readme): update installation instructions
test(trading): add unit tests for risk management
refactor(api): simplify order placement logic
```

---

## 🔃 Pull Request

### Template de PR:

```markdown
## 📝 Descrição
Breve descrição do que foi feito.

## 🎯 Tipo de Mudança
- [ ] Bug fix
- [ ] Nova feature
- [ ] Breaking change
- [ ] Documentação

## ✅ Checklist
- [ ] Código segue style guidelines
- [ ] Testes adicionados/atualizados
- [ ] Documentação atualizada
- [ ] Sem warnings de lint
- [ ] Mudanças testadas localmente

## 📸 Screenshots (se aplicável)
[Se relevante, adicione screenshots]

## 🔗 Issues Relacionadas
Fixes #123
```

### Critérios de Aceitação:
- ✅ Código bem formatado e documentado
- ✅ Todos os testes passam
- ✅ Sem conflitos com a branch principal
- ✅ Aprovação de pelo menos 1 mantenedor

---

## 🐛 Reporte de Bugs

Antes de abrir uma issue, verifique se já não foi reportada.

### Template de Bug:

```markdown
## 🔍 Descrição do Bug
[Descrição clara e concisa]

## 🔄 Como Reproduzir
1. [Passo 1]
2. [Passo 2]
3. [Passo 3]

## 📌 Comportamento Esperado
[O que deveria acontecer]

## ❌ Comportamento Atual
[O que realmente acontece]

## 🖥️ Ambiente
- OS: [Windows/Linux/Mac]
- Python: [versão]
- Dependências: [listar se aplicável]

## 📎 Contexto Adicional
[Qualquer informação adicional relevante]
```

---

## ✨ Solicitação de Features

### Template de Feature:

```markdown
## 🎯 Descrição
[Descrição clara da feature desejada]

## 💡 Caso de Uso
[Por que isso seria útil?]

## 🔧 Implementação Sugerida
[Se tiver ideias, compartilhe]

## 📊 Impacto
- Performance: [Alto/Médio/Baixo]
- Complexidade: [Alta/Média/Baixa]
- Breaking change: [Sim/Não]
```

---

## 📚 Padrões de Código

### Python

```python
# ✅ Bom
def calculate_position_size(account_balance: float, risk_percent: float) -> float:
    """
    Calculate position size based on account balance and risk percentage.
    
    Args:
        account_balance: Total account balance in USD
        risk_percent: Risk percentage (0-100)
    
    Returns:
        Position size in lots
    """
    return (account_balance * risk_percent / 100) / 100000


# ❌ Evitar
def calc_pos(bal, risk):
    return (bal * risk / 100) / 100000
```

### Naming Conventions

```python
# Classes - PascalCase
class TradingBot:
    pass

# Funções/Métodos - snake_case
def execute_trade():
    pass

# Constantes - UPPER_SNAKE_CASE
MAX_LEVERAGE = 50
DEFAULT_RISK = 2.0

# Private/Protected - _leading_underscore
def _internal_calculation():
    pass
```

---

## 🔗 Links Úteis

- [Python PEP 8](https://www.python.org/dev/peps/pep-0008/) - Style Guide
- [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Docs - PRs](https://docs.github.com/en/pull-requests)

---

## ❓ Dúvidas?

- 💬 Abra uma [Discussion](https://github.com/LucasPedroso96/Portfolio-Software-Engineer/discussions)
- 🔗 Me contate via [LinkedIn](https://www.linkedin.com/in/lucas-pedroso-96)
- 📧 Abra uma [Issue](https://github.com/LucasPedroso96/Portfolio-Software-Engineer/issues)

---

**Obrigado por contribuir!** ❤️

Última atualização: Setembro 4, 2026
