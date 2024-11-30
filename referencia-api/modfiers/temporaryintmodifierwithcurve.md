# TemporaryIntModifierWithCurve

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `TemporaryIntModifierWithCurve` estende `TemporaryIntModifier` e utiliza uma curva de animação (`AnimationCurve`) para ajustar dinamicamente o valor do modificador inteiro ao longo do tempo, com base no progresso do temporizador.

***

### Propriedades:

| Nome           | Tipo  | Descrição                                                                                            |
| -------------- | ----- | ---------------------------------------------------------------------------------------------------- |
| `CurrentValue` | `int` | O valor atual do modificador, ajustado com base no progresso do temporizador e na curva de animação. |

***

### Construtores:

| Nome                                                                                                                                                                                     | Descrição                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `TemporaryIntModifierWithCurve(ModifierCalculationType type, int value, float durationInSeconds, object source, AnimationCurve curve, ModifierStrategy<int> calculationStrategy = null)` | Inicializa um modificador temporário inteiro com curva de animação, tipo de cálculo, valor base, duração, fonte e estratégia opcional. |

***
