---
icon: file
---

# Modifier\<TValue>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe genérica abstrata `Modifier<TValue>` estende `ModifierBase` e representa um modificador que altera valores dinâmicos usando estratégias específicas de cálculo. É projetada para suportar tipos numéricos.

***

### Propriedades:

| Nome                  | Tipo                  | Descrição                                                     |
| --------------------- | --------------------- | ------------------------------------------------------------- |
| `CurrentValue`        | `TValue`              | O valor atual do modificador, geralmente igual ao valor base. |
| `baseValue`           | `TValue`              | O valor base do modificador antes de qualquer cálculo.        |
| `CalculationStrategy` | `ModifierStrategy<T>` | A estratégia de cálculo associada a este modificador.         |

***

### Construtores:

| Nome                                                                                                                       | Descrição                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| `Modifier(ModifierCalculationType type, TValue value, object source, ModifierStrategy<TValue> calculationStrategy = null)` | Inicializa um novo modificador com tipo de cálculo, valor base, fonte e uma estratégia opcional. |

***

### Métodos Públicos:

| Nome                                                        | Retorno  | Descrição                                                     |
| ----------------------------------------------------------- | -------- | ------------------------------------------------------------- |
| `SetStrategy(ModifierStrategy<TValue> calculationStrategy)` | `void`   | Define uma nova estratégia de cálculo para o modificador.     |
| `GetValue()`                                                | `object` | Retorna o valor atual do modificador como um objeto genérico. |

***
