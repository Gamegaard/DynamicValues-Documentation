---
icon: file
---

# DynamicTimedFloatRangeWithCurve

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `DynamicTimedFloatRangeWithCurve` estende `DynamicTimedFloatRange`, adicionando uma curva de animação (`AnimationCurve`) para ajustar dinamicamente as alterações de valores ao longo do tempo. Ideal para sistemas que necessitam de mudanças não lineares controladas por uma curva.

***

### Propriedades:

| Nome         | Tipo             | Descrição                                                     |
| ------------ | ---------------- | ------------------------------------------------------------- |
| `ValueCurve` | `AnimationCurve` | Curva que controla como o valor é ajustado ao longo do tempo. |

***

### Construtores:

| Nome                                                                                                                                                                                   | Descrição                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| `DynamicTimedFloatRangeWithCurve()`                                                                                                                                                    | Construtor padrão que inicializa a classe com valores padrão.                                          |
| `DynamicTimedFloatRangeWithCurve(float baseValue, float currentValue, float changeBaseValue, float changeTime, AnimationCurve valueCurve, bool isPaused = false, float timeScale = 1)` | Inicializa a classe com valores base, valores atuais, alterações base, intervalo de tempo e uma curva. |
| `DynamicTimedFloatRangeWithCurve(DynamicTimedFloatRangeWithCurve other)`                                                                                                               | Construtor de cópia que cria uma nova instância com base em outra existente.                           |

***

### Métodos Públicos:

| Nome                   | Retorno  | Descrição                                                                                                    |
| ---------------------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| `UpdateChangedValue()` | `bool`   | Atualiza o valor atual com base no temporizador e na curva de valor. Retorna `true` se o valor foi alterado. |
| `ToString()`           | `string` | Retorna uma representação em texto do estado atual, incluindo a avaliação da curva de animação.              |

***
