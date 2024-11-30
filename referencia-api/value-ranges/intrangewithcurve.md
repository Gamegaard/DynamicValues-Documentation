# IntRangeWithCurve

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `IntRangeWithCurve` estende a funcionalidade de `IntRange`, adicionando uma curva de animação (`AnimationCurve`) para ajustar dinamicamente o valor atual com base em uma porcentagem ao longo do tempo.

***

### Propriedades:

| Nome         | Tipo             | Descrição                                                                 |
| ------------ | ---------------- | ------------------------------------------------------------------------- |
| `ValueCurve` | `AnimationCurve` | Curva que controla como o valor atual é ajustado com base na porcentagem. |

***

### Construtores:

| Nome                                                                                         | Descrição                                                                                      |
| -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `IntRangeWithCurve()`                                                                        | Construtor padrão que inicializa a classe com valores padrão.                                  |
| `IntRangeWithCurve(int maxValue, int currentValue, int minValue, AnimationCurve valueCurve)` | Inicializa o intervalo com valores máximos, mínimos, atuais e uma curva de animação associada. |
| `IntRangeWithCurve(IntRangeWithCurve other)`                                                 | Construtor de cópia que cria um novo intervalo com base em outra instância existente.          |

***

### Métodos Públicos:

| Nome                                | Retorno  | Descrição                                                                                                  |
| ----------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| `SetToPercentage(float percentage)` | `void`   | Define o valor atual com base em uma porcentagem, modificada pela curva de animação associada.             |
| `ToString()`                        | `string` | Retorna uma representação em texto do estado atual da `IntRangeWithCurve`, incluindo a avaliação da curva. |
