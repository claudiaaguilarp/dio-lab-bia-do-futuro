# Base de Conhecimento

## Dados Utilizados

Os dados utilizados estão disponíveis na pasta `data`.

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados:

Expandi os dados atualizando com novos padrões de consumo e histórico de atendimento.

---

## Estratégia de Integração

### Como os dados são carregados:

Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt

### Como os dados são usados no prompt:

A medida que o usuário vai perguntando ele vai consultando dinamicamente a base para aprofundar sua resposta.

---

## Exemplo de Contexto Montado

Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 05/11: Streaming - R$ 105,90
...
