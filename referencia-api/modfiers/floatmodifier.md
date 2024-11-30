---
icon: file
---

# FloatModifier

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `FloatModifier` estende `Modifier<float>` e representa um modificador que opera sobre valores de ponto flutuante (`float`). É usada para ajustar dinamicamente valores de ponto flutuante em sistemas baseados em modificadores.

***

### Propriedades:

| Nome       | Tipo   | Descrição                                                       |
| ---------- | ------ | --------------------------------------------------------------- |
| `HasValue` | `bool` | Indica se o modificador possui um valor base diferente de zero. |

***

### Construtores:

| Nome                                                                                                                          | Descrição                                                                                                  |
| ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `FloatModifier(ModifierCalculationType type, float value, object source, ModifierStrategy<float> calculationStrategy = null)` | Inicializa um modificador de ponto flutuante com tipo de cálculo, valor base, fonte e estratégia opcional. |

***
