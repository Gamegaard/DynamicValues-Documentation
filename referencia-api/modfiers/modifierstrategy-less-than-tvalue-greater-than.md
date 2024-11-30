---
icon: file
---

# ModifierStrategy\<TValue>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe abstrata genérica `ModifierStrategy<TValue>` estende `ModifierStrategyBase` e define a lógica para aplicar modificadores a valores dinâmicos. É projetada para suportar tipos numéricos e fornece métodos auxiliares para cálculos e filtragem de modificadores.

***

### Métodos Públicos:

| Nome                                                                  | Retorno  | Descrição                                                                                                            |
| --------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------- |
| `Apply(DynamicValue<TValue> dynamicValue, Modifier<TValue> modifier)` | `TValue` | Aplica a lógica de cálculo para um modificador baseado no valor dinâmico e propriedades do modificador. _(Abstrato)_ |

***

### Métodos Protegidos:

| Nome                                                                                  | Retorno                  | Descrição                                                                             |
| ------------------------------------------------------------------------------------- | ------------------------ | ------------------------------------------------------------------------------------- |
| `NormalizedValue(float value)`                                                        | `float`                  | Normaliza um valor dividindo-o por 100, retornando o resultado como uma fração de 1.  |
| `GetModifiersByType(DynamicValue<TValue> dynamicValue, ModifierCalculationType type)` | `List<Modifier<TValue>>` | Retorna uma lista de modificadores de um tipo específico aplicados ao valor dinâmico. |

***
