# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

> [!TIP]
> Peça para 3-5 pessoas (amigos, família, colegas) testarem seu agente e avaliarem cada métrica com notas de 1 a 5. Isso torna suas métricas mais confiáveis! Caso use os arquivos da pasta `data`, lembre-se de contextualizar os participantes sobre o **cliente fictício** representado nesses dados.

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `transacoes.csv`
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Produto compatível com o perfil do cliente
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende o produto BBDC3 na Bovespa?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resultado:** [x] Correto  [ ] Incorreto

---

## Formulário de Feedback

Use com os participantes do teste:

| Métrica | Pergunta | Nota (1-5) |
|---------|----------|------------|
| Assertividade | "A resposta respondeu sua pergunta?" | 4 |
| Segurança | "As informações pareceram confiáveis" | 4 |
| Coerência | "A linguagem foi clara e fácil e fácil de entender?" | 4 |

**Comentário aberto:** O que poderia melhorar?

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- Identificação de intenção: O agente diferenciou corretamente perguntas sobre gastos reais de pedidos de recomendação.
- Manutenção do escopo: Bloqueou com sucesso perguntas irrelevantes (como clima), mantendo a autoridade no tema financeiro.
- Extração de dados: A leitura do transacoes.csv foi precisa, somando corretamente os valores por categoria.
- Tom de voz: A linguagem manteve-se profissional e acessível, conforme esperado para o perfil bancário/financeiro.

**O que pode melhorar:**
- Tratamento de exceções: Quando o usuário pergunta sobre ativos muito específicos (como BBDC3), o agente poderia sugerir onde encontrar essa informação em vez de apenas dizer que não sabe.
- Contexto de histórico: O agente ainda tem dificuldade em lembrar a pergunta anterior (ex: "E quanto gastei com transporte?" logo após a pergunta de alimentação).
- Personalização: As recomendações de investimento poderiam ser mais detalhadas, explicando o "porquê" da escolha baseada no perfil.
