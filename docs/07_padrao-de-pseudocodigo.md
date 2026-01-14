# Padrão de Pseudocódigo do CRM

Este projeto usa pseudocódigo como linguagem intermediária:
natural, porém estruturada e sem ambiguidade.

## Regras do Pseudocódigo

1. Toda rotina deve ter: Início → Passos → Fim
2. Instruções devem ser concisas no formato:
   acao(parametro1, parametro2, ...)
3. Comentários de bloco usam:
   // Nome do bloco
4. Variáveis simples são permitidas:
   nome_variavel = valor
5. Entradas devem ser explícitas no início:
   entrada(cliente_id, descricao, ...)
6. Validações são escritas como:
   verificar(regra, contexto)
7. Quando uma regra falhar, registrar o bloqueio:
   bloquear(acao, motivo)
8. Sem sintaxe de linguagem (sem if/else, sem loops).
   Usar linguagem estruturada:
   "caso regra falhe" / "caso regra passe" apenas como texto curto.

## Estruturas Lógicas Permitidas

### Decisão (Condicional)
Usar a estrutura:

SE (condicao)
  executar_acoes
SENÃO
  executar_acoes_alternativas
FIM_SE

### Repetição (Laço)
Usar a estrutura:

ENQUANTO (condicao)
  executar_bloco
FIM_ENQUANTO

PARA_CADA (item EM conjunto)
  executar_bloco
FIM_PARA

## Variáveis e Operações

- Variáveis representam valores armazenados durante a execução do algoritmo.
- Atribuição é feita com o operador "=".

Exemplos:
variavel_texto = "valor"
variavel_inteiro = 3
variavel_decimal = 2.5
variavel_booleana = verdadeiro

## Operações Permitidas

- Soma: a + b
- Subtração: a - b
- Multiplicação: a * b
- Divisão: a / b
- Comparação: =, !=, >, <, >=, <=

Operações devem ser simples e legíveis,
evitando qualquer ambiguidade.

## Operadores e Expressões Lógicas

### Operadores Aritméticos
- +  soma
- -  subtração
- *  multiplicação
- /  divisão
- %  resto da divisão

### Operadores Relacionais
- =   igual
- !=  diferente
- >   maior
- <   menor
- >=  maior ou igual
- <=  menor ou igual

### Operadores Lógicos
- E    → todas as condições devem ser verdadeiras
- OU   → pelo menos uma condição verdadeira
- NÃO  → inverte o valor lógico

### Expressões Compostas
Condições podem ser combinadas:

SE (condicao_A E condicao_B)
SE (condicao_A OU_

## Padrão de Estrutura dos Algoritmos

Todo algoritmo do CRM deve seguir:

// Input
(definir entradas do usuário e referências internas)

// Processamento
(regras + operações + decisões)

// Output
(resultado final e registros)

## Funções (Definição, Chamada e Retorno)

### Definição
funcao nome_funcao(param1, param2):
  (passos)
  retornar valor
fim_funcao

### Chamada
resultado = nome_funcao(valor1, valor2)
