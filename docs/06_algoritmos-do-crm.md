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

## Algoritmo B — Atualizar Status de Demanda

Início:
- Receber identificação da demanda e novo status

Passos:
1. Localizar a demanda correspondente
2. Verificar se a mudança de status é permitida
3. Atualizar o status da demanda
4. Registrar a alteração no histórico

Fim:
- Status atualizado com histórico preservado

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
