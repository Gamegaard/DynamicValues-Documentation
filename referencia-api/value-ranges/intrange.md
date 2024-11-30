---
icon: file
---

# IntRange

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `IntRange` representa um intervalo de valores inteiros, com métodos utilitários para gerenciar e calcular valores dentro do intervalo. É uma implementação concreta de `ValueRange<int>`.

***

### Propriedades:

| Nome                | Tipo    | Descrição                                                                                               |
| ------------------- | ------- | ------------------------------------------------------------------------------------------------------- |
| `Percentage`        | `float` | Retorna a porcentagem do valor atual em relação ao máximo.                                              |
| `InversePercentage` | `float` | Retorna o complemento da porcentagem atual (1 - Percentage).                                            |
| `IsFull`            | `bool`  | Indica se o valor atual é maior ou igual ao máximo.                                                     |
| `HasValue`          | `bool`  | Indica se o valor atual é maior que 0.                                                                  |
| `IsZero`            | `bool`  | Indica se o valor atual é igual a 0.                                                                    |
| `MissingValue`      | `int`   | Calcula a diferença entre o valor máximo e o valor atual.                                               |
| `CurrentValue`      | `int`   | Define ou obtém o valor atual do intervalo, garantindo que esteja dentro dos limites mínimos e máximos. |

***

### Construtores:

| Nome                                                         | Descrição                                                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `IntRange()`                                                 | Construtor padrão que inicializa o intervalo com os valores padrão do tipo `int`.                |
| `IntRange(ValueRange<int> other)`                            | Construtor de cópia que cria um intervalo com base em outro intervalo de tipo `ValueRange<int>`. |
| `IntRange(int maxValue, int currentValue, int minValue = 0)` | Inicializa o intervalo com valores máximos, mínimos e atuais especificados.                      |

***

### Métodos Públicos:

| Nome                                | Retorno | Descrição                                                                              |
| ----------------------------------- | ------- | -------------------------------------------------------------------------------------- |
| `SetToPercentage(float percentage)` | `void`  | Define o valor atual com base em uma porcentagem em relação ao intervalo especificado. |
