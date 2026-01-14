# Funções do CRM (Pseudocódigo)

Este documento define funções reutilizáveis (mini-algoritmos)
para sustentar os algoritmos do CRM.

As funções recebem parâmetros e retornam valores,
permitindo modularidade e reutilização.

---

## Funções de Consulta (Estado)

funcao obter_status(demanda_id):
  retornar status_atual_da_demanda

funcao obter_responsavel(demanda_id):
  retornar responsavel_da_demanda

funcao contar_demandas(cliente_id):
  retornar quantidade_demandas

---

## Funções de Validação (Regras)

funcao verificar_responsavel(demanda_id):
  responsavel = obter_responsavel(demanda_id)
  SE (responsavel != "vazio")
    retornar verdadeiro
  SENÃO
    retornar falso
  FIM_SE

funcao transicao_permitida(status_atual, novo_status):
  // regra simples (placeholder lógico)
  // exemplo: não permitir sair de "concluida"
  SE (status_atual = "concluida")
    retornar falso
  SENÃO
    retornar verdadeiro
  FIM_SE

---

## Funções de Ação (Efeitos)

funcao definir_status(demanda_id, novo_status):
  // em fase lógica: representa a ação
  registrar_historico("status_definido", demanda_id, novo_status)
  retornar verdadeiro

funcao registrar_historico(evento, alvo, detalhe):
  // em fase lógica: representa registro
  retornar verdadeiro
