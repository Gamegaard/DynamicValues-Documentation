# DynamicInt

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `DynamicInt` representa um valor dinâmico do tipo inteiro (`int`), que pode ser modificado por modificadores temporários e permanentes. Suporta estratégias de cálculo complexas para ajustar o valor final dinamicamente.

***

### Propriedades:

| Nome           | Tipo  | Descrição                                                     |
| -------------- | ----- | ------------------------------------------------------------- |
| `MaximumValue` | `int` | O valor máximo permitido após aplicar todos os modificadores. |
| `MinimumValue` | `int` | O valor mínimo permitido após aplicar todos os modificadores. |

***

### Construtores:

| Nome                           | Descrição                                                                           |
| ------------------------------ | ----------------------------------------------------------------------------------- |
| `DynamicInt()`                 | Construtor padrão que inicializa o valor dinâmico com valores padrão.               |
| `DynamicInt(int baseValue)`    | Inicializa o valor dinâmico com um valor base especificado.                         |
| `DynamicInt(DynamicInt other)` | Construtor de cópia que cria um novo valor dinâmico com base em outro já existente. |

***

### Métodos Protegidos:

| Nome                                                                                      | Retorno | Descrição                                                                  |
| ----------------------------------------------------------------------------------------- | ------- | -------------------------------------------------------------------------- |
| `CalculateFinalValue<T>(List<TemporaryModifier<int>> tempMods, List<Modifier<int>> mods)` | `int`   | Calcula o valor final considerando todos os modificadores aplicados.       |
| `SumValueWithMode(int value, Modifier<int> mod)`                                          | `int`   | Soma um modificador ao valor base considerando seu tipo de cálculo.        |
| `SubtractValues(int value1, int value2)`                                                  | `int`   | Subtrai dois valores do tipo inteiro.                                      |
| `EvaluateModValue(Modifier<int> mod)`                                                     | `int`   | Avalia o valor de um modificador com base no tipo de cálculo especificado. |
| `GetAllFlat()`                                                                            | `int`   | Calcula o valor total de modificadores do tipo `Flat`.                     |

***

### Estratégias de Cálculo de Modificadores:

| Tipo                | Descrição                                                                     |
| ------------------- | ----------------------------------------------------------------------------- |
| `Flat`              | Modificador aplicado diretamente como um valor fixo.                          |
| `BasePercentage`    | Calculado como uma porcentagem do valor base.                                 |
| `OverallPercentage` | Calculado como uma porcentagem do valor base somado aos modificadores `Flat`. |
