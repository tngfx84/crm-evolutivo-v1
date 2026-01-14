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
