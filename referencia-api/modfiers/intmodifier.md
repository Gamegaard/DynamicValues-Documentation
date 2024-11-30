---
icon: file
---

# IntModifier

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `IntModifier` estende `Modifier<int>` e representa um modificador que opera sobre valores inteiros (`int`). É usada para ajustar dinamicamente valores inteiros em sistemas baseados em modificadores.

***

### Propriedades:

| Nome       | Tipo   | Descrição                                                       |
| ---------- | ------ | --------------------------------------------------------------- |
| `HasValue` | `bool` | Indica se o modificador possui um valor base diferente de zero. |

***

### Construtores:

| Nome                                                                                                                    | Descrição                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `IntModifier(ModifierCalculationType type, int value, object source, ModifierStrategy<int> calculationStrategy = null)` | Inicializa um modificador inteiro com tipo de cálculo, valor base, fonte e estratégia opcional. |

***
