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

## Algoritmo B — Atualizar Status de Demanda (com Validação)

Início:
- Receber identificação da demanda e status desejado

Passos:
1. Identificar o estado atual da demanda
2. Verificar se a demanda possui responsável definido
3. Verificar se o status desejado é compatível com o estado atual
4. Caso alguma regra seja violada, impedir a atualização
5. Caso as regras sejam respeitadas, atualizar o status
6. Registrar a mudança no histórico

Fim:
- Status atualizado ou mudança bloqueada com registro

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

## Conceito de Estado e Validação

Os algoritmos do CRM consideram o estado atual do sistema
como base para decisões.

Estado representa a situação de uma entidade em um determinado momento,
como o status de uma demanda, a maturidade do cliente ou o andamento de um processo.

Antes de executar qualquer ação relevante, o algoritmo valida
se as regras do sistema continuam sendo respeitadas.

---

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
