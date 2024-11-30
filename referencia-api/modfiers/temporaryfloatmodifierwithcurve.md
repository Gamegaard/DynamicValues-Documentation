---
icon: file
---

# TemporaryFloatModifierWithCurve

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `TemporaryFloatModifierWithCurve` estende `TemporaryFloatModifier` e utiliza uma curva de animação (`AnimationCurve`) para ajustar dinamicamente o valor do modificador ao longo do tempo, com base no progresso do temporizador.

***

### Propriedades:

| Nome           | Tipo             | Descrição                                                                                            |
| -------------- | ---------------- | ---------------------------------------------------------------------------------------------------- |
| `valueCurve`   | `AnimationCurve` | A curva de animação usada para ajustar o valor do modificador ao longo do tempo.                     |
| `CurrentValue` | `float`          | O valor atual do modificador, ajustado com base no progresso do temporizador e na curva de animação. |

***

### Construtores:

| Nome                                                                                                                                                                                           | Descrição                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `TemporaryFloatModifierWithCurve(ModifierCalculationType type, float value, float durationInSeconds, object source, AnimationCurve curve, ModifierStrategy<float> calculationStrategy = null)` | Inicializa um modificador temporário com curva de animação, tipo de cálculo, valor base, duração, fonte e estratégia opcional. |

***
