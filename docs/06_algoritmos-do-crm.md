# Algoritmos do CRM (Lógica Estruturada)

Este documento descreve algoritmos do CRM em linguagem natural estruturada.
Os algoritmos representam regras de negócio como sequências finitas,
ordenadas e executáveis de instruções.

Ainda não há código nem linguagem formal.

---

## Algoritmo A — Registrar Nova Demanda

Início:
- Receber dados básicos da demanda e do cliente

Passos:
1. Verificar se o cliente já existe
2. Caso não exista, registrar cliente
3. Registrar a nova demanda associada ao cliente
4. Definir status inicial da demanda
5. Registrar a ação no histórico

Fim:
- Demanda registrada, associada e rastreável

---

## Algoritmo B — Atualizar Status de Demanda (com variáveis)

Início:
- Entrada: demanda_id, novo_status

// Estado atual
status_atual = obter_status(demanda_id)
responsavel_existe = verificar_responsavel(demanda_id)

// Validações
SE (responsavel_existe = falso)
  bloquear("atualizar_status", "demanda_sem_responsavel")
  registrar_historico("bloqueio", demanda_id)
  FIM
FIM_SE

SE (status_atual = "concluida")
  bloquear("atualizar_status", "demanda_ja_concluida")
  registrar_historico("bloqueio", demanda_id)
  FIM
FIM_SE

// Atualização
definir_status(demanda_id, novo_status)
registrar_historico("status_atualizado", demanda_id)

Fim

---

## Algoritmo C — Identificar Crescimento de Complexidade

Início:
- Avaliar volume de clientes, demandas e interações

Passos:
1. Verificar aumento de repetição de demandas
2. Verificar aumento de responsáveis envolvidos
3. Identificar impacto operacional crescente
4. Tornar visível a necessidade de maior controle

Fim:
- Consciência do nível de maturidade atual

---

## Algoritmo D — Encerrar Demanda com Segurança

Início:
- Solicitação de encerramento de demanda

Passos:
1. Identificar o estado atual da demanda
2. Verificar se todas as etapas obrigatórias foram concluídas
3. Verificar se existe histórico suficiente da execução
4. Caso alguma verificação falhe, impedir o encerramento
5. Caso todas as verificações sejam atendidas, encerrar a demanda
6. Registrar o encerramento no histórico

Fim:
- Demanda encerrada com segurança e rastreabilidade

---

## Algoritmo E — Acompanhar Demandas Até Conclusão

Início:
- Conjunto de demandas ativas

Passos:
ENQUANTO (existir demanda com status diferente de "concluída")
  PARA_CADA (demanda EM demandas_ativas)
    verificar_status(demanda)
    SE (status = "pendente")
      notificar_responsavel(demanda)
    SENÃO SE (status = "em_execucao")
      acompanhar_prazo(demanda)
    FIM_SE
  FIM_PARA
FIM_ENQUANTO

Fim:
- Todas as demandas concluídas

---

## Algoritmo F — Classificar Demanda por Regra

Início:
- Demanda registrada

Passos:
SE (demanda.tipo = "recorrente")
  classificar(demanda, "padrao")
SENÃO
  classificar(demanda, "excepcional")
FIM_SE

registrar_historico("demanda_classificada", demanda)

Fim:
- Demanda classificada e registrada

---

## Algoritmo G — Avaliar Complexidade do Cliente

Início:
- Entrada: cliente_id

// Variáveis
quantidade_demandas = contar_demandas(cliente_id)
quantidade_responsaveis = contar_responsaveis(cliente_id)

// Avaliação
SE (quantidade_demandas > 10)
  nivel_complexidade = "medio"
SENÃO
  nivel_complexidade = "baixo"
FIM_SE

registrar_historico("complexidade_avaliada", cliente_id, nivel_complexidade)

Fim

## Conceito de Estado e Validação

Os algoritmos do CRM consideram o estado atual do sistema
como base para decisões.

Estado representa a situação de uma entidade em um determinado momento,
como o status de uma demanda, a maturidade do cliente ou o andamento de um processo.

Antes de executar qualquer ação relevante, o algoritmo valida
se as regras do sistema continuam sendo respeitadas.


# Representação em Pseudocódigo (Primeira Camada)

## Pseudocódigo A — Registrar Nova Demanda

// Entradas
entrada(cliente_identificacao, descricao_demanda)

// Preparação
cliente_existe = verificar_existencia_cliente(cliente_identificacao)

// Registro de cliente (se necessário)
caso cliente_existe falhe:
  criar_cliente(cliente_identificacao)
  registrar_historico("cliente_criado", cliente_identificacao)

// Registro de demanda
demanda_id = criar_demanda(cliente_identificacao, descricao_demanda)
definir_status(demanda_id, "aberta")
registrar_historico("demanda_criada", demanda_id)

// Finalização
retornar(demanda_id)
fim

## Pseudocódigo B — Atualizar Status de Demanda (com validação)

// Entradas
entrada(demanda_id, novo_status)

// Estado atual
status_atual = obter_status(demanda_id)
responsavel = obter_responsavel(demanda_id)

// Validações
regra_responsavel = verificar("demanda_tem_responsavel", responsavel)
regra_transicao = verificar("transicao_permitida", status_atual, novo_status)

caso regra_responsavel falhe:
  bloquear("atualizar_status", "sem_responsavel")
  registrar_historico("status_bloqueado", demanda_id)
  fim

caso regra_transicao falhe:
  bloquear("atualizar_status", "transicao_invalida")
  registrar_historico("status_bloqueado", demanda_id)
  fim

// Atualização
definir_status(demanda_id, novo_status)
registrar_historico("status_atualizado", demanda_id)

// Finalização
fim
