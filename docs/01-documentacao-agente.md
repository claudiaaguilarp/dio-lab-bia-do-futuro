# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

O agente é um educador financeiro que alerta sobre gastos e despesas exageradas e indica como usar melhor seu dinheiro focado em rentabilidade.

### Solução
> Como o agente resolve esse problema de forma proativa?

Ele tira dúvidas de como investir seu dinheiro e se no período indicado ouve excesso de gastos baseado em suas entradas e saidas. 

### Público-Alvo
> Quem vai usar esse agente?

Qualquer pessoa que tenha dificuldades para controle de entrada e saída de dinheiro e queira e não sabe como investir seu dinheiro. 

---

## Persona e Tom de Voz

### Nome do Agente
Edu

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

O agente será educativo com uma pegada mais direta fazendo que o usuário consiga naquela momento se envolver de forma racional e atinja a saúde financeira que deseja.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Terá uma comunicação formal mas acessível para que todas as pessoas de diversos níveis de conhecimenot consiga entender e atingir o objetivo que é a educação financeira. 

### Exemplos de Linguagem
- Saudação: [ex: "Olá! Como posso te ajudar a conseguir sua educação financeira hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com..."]

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Chatbot em Streamlit |
| LLM | GPT-4 via API |
| Base de Conhecimento | JSON/CSV com dados do cliente |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [x] Agente só responde com base nos dados fornecidos
- [x] Respostas incluem fonte da informação
- [x] Quando não sabe, admite e redireciona
- [x] Não faz recomendações de investimento sem perfil do cliente
- [x] Não faz análise de gastos sem perfil do cliente
- [x] Somente responde perguntas que envolvem recomendações de investimentos ou análise de gastos
- [x] Usa somente base do perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

- Ele não indica em qual investimento deve fazer
- Não decide como deve ser seus pagamentos, apenas analisa.
- Não conversa sobre outras assuntos que não sejam sobre educação financeira
- Não informa dados sensíveis
- Não busca informações na rede para analise.
