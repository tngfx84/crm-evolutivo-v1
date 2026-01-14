# Ciclo de Processamento (Input → Processamento → Output)

Este documento define o padrão de escrita dos algoritmos do CRM
com base no ciclo de processamento: entradas, operações internas e saídas.

---

## 1) Input (Entradas)

Entradas podem vir de duas fontes:

### 1.1 Entrada da pessoa usuária
- dados informados durante uma ação (ex.: idade, escolha, confirmação)

### 1.2 Valores internos de referência
- valores definidos pelo sistema (ex.: preço_total, regra de maturidade, limites)

Regra: toda entrada deve ser explícita e nomeada.

---

## 2) Processamento

O processamento é a execução das regras de negócio:
- decisões (SE / SENÃO)
- operações aritméticas (+, -, *, /, %)
- comparações (>=, <=, =, !=)
- operadores lógicos (E, OU, NÃO)

Regra: toda regra deve ser legível e sem ambiguidade.

---

## 3) Output (Saídas)

Saídas são resultados produzidos pelo algoritmo:
- valores calculados (ex.: preco_aplicado)
- classificações (ex.: risco = "alto")
- mensagens (ex.: "Meia-entrada aplicada")
- registros no histórico (ex.: "status_atualizado")

Regra: toda saída deve estar claramente indicada.

---

## 4) Ajuste Lógico (Testar → Avaliar → Ajustar)

Quando uma condição foi esquecida ou mal definida:
1. registrar o problema encontrado
2. identificar a regra que faltou
3. ajustar o pseudocódigo
4. registrar o ajuste como revisão do algoritmo

Obs.: isso é refinamento lógico do algoritmo, não antecipação técnica.
