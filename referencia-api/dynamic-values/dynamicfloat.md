# DynamicFloat

## DynamicFloat

#### Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `DynamicFloat` representa um valor dinâmico do tipo `float`, que pode ser modificado por modificadores temporários e permanentes. Oferece suporte a estratégias de cálculo complexas e ajusta automaticamente o valor final com base nos modificadores aplicados.

***

### Propriedades:

| Nome           | Tipo    | Descrição                                                     |
| -------------- | ------- | ------------------------------------------------------------- |
| `MaximumValue` | `float` | O valor máximo permitido após aplicar todos os modificadores. |
| `MinimumValue` | `float` | O valor mínimo permitido após aplicar todos os modificadores. |

***

### Construtores:

| Nome                               | Descrição                                                                           |
| ---------------------------------- | ----------------------------------------------------------------------------------- |
| `DynamicFloat()`                   | Construtor padrão que inicializa o valor dinâmico com valores padrão.               |
| `DynamicFloat(float baseValue)`    | Inicializa o valor dinâmico com um valor base especificado.                         |
| `DynamicFloat(DynamicFloat other)` | Construtor de cópia que cria um novo valor dinâmico com base em outro já existente. |

***

### Métodos Protegidos:

| Nome                                                                                          | Retorno | Descrição                                                                  |
| --------------------------------------------------------------------------------------------- | ------- | -------------------------------------------------------------------------- |
| `CalculateFinalValue<T>(List<TemporaryModifier<float>> tempMods, List<Modifier<float>> mods)` | `float` | Calcula o valor final considerando todos os modificadores aplicados.       |
| `SumValueWithMode(float value, Modifier<float> mod)`                                          | `float` | Soma um modificador ao valor base considerando seu tipo de cálculo.        |
| `SubtractValues(float value1, float value2)`                                                  | `float` | Subtrai dois valores do tipo `float`.                                      |
| `EvaluateModValue(Modifier<float> mod)`                                                       | `float` | Avalia o valor de um modificador com base no tipo de cálculo especificado. |
| `GetAllFlat()`                                                                                | `float` | Calcula o valor total de modificadores do tipo `Flat`.                     |

***

### Estratégias de Cálculo de Modificadores:

| Tipo                    | Descrição                                                                                 |
| ----------------------- | ----------------------------------------------------------------------------------------- |
| `Flat`                  | Modificador aplicado diretamente como um valor fixo.                                      |
| `BasePercentage`        | Calculado como uma porcentagem do valor base.                                             |
| `OverallPercentage`     | Calculado como uma porcentagem do valor final após aplicar todos os outros modificadores. |
| `OverallFlatPercentage` | Calculado como uma porcentagem do valor base somado aos modificadores `Flat`.             |
| `Custom`                | Utiliza uma estratégia de cálculo personalizada definida pelo modificador.                |
