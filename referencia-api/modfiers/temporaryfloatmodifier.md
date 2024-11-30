---
icon: file
---

# TemporaryFloatModifier

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `TemporaryFloatModifier` estende `TemporaryModifier<float>` e representa um modificador temporário do tipo `float`, que expira após uma duração especificada. É ideal para efeitos temporários que modificam valores dinâmicos.

***

### Propriedades:

| Nome       | Tipo   | Descrição                                                       |
| ---------- | ------ | --------------------------------------------------------------- |
| `HasValue` | `bool` | Indica se o modificador possui um valor base diferente de zero. |

***

### Construtores:

| Nome                                                                                                                                                            | Descrição                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `TemporaryFloatModifier(ModifierCalculationType type, float value, float durationInSeconds, object source, ModifierStrategy<float> calculationStrategy = null)` | Inicializa um novo modificador temporário com tipo de cálculo, valor base, duração, fonte e estratégia opcional. |

***
