# FloatRangeWithCurve

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `FloatRangeWithCurve` é uma extensão de `FloatRange` que adiciona uma curva de animação (`AnimationCurve`) para ajustar dinamicamente o valor atual com base em uma porcentagem ao longo do tempo. Isso é útil para sistemas que exigem variações de valores controladas por uma curva.

***

### Propriedades:

| Nome         | Tipo             | Descrição                                                                 |
| ------------ | ---------------- | ------------------------------------------------------------------------- |
| `ValueCurve` | `AnimationCurve` | Curva que controla como o valor atual é ajustado com base na porcentagem. |

***

### Construtores:

| Nome                                                                                                 | Descrição                                                                                      |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `FloatRangeWithCurve()`                                                                              | Construtor padrão que inicializa a classe com valores padrão.                                  |
| `FloatRangeWithCurve(float maxValue, float currentValue, float minValue, AnimationCurve valueCurve)` | Inicializa o intervalo com valores máximos, mínimos, atuais e uma curva de animação associada. |
| `FloatRangeWithCurve(FloatRangeWithCurve other)`                                                     | Construtor de cópia que cria um novo intervalo com base em outra instância existente.          |

***

### Métodos Públicos:

| Nome                                | Retorno  | Descrição                                                                                                    |
| ----------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| `SetToPercentage(float percentage)` | `void`   | Define o valor atual com base em uma porcentagem, modificada pela curva de animação associada.               |
| `ToString()`                        | `string` | Retorna uma representação em texto do estado atual da `FloatRangeWithCurve`, incluindo a avaliação da curva. |
