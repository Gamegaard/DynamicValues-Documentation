---
icon: file
---

# ValueRange\<TValue>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `ValueRange<T>` é uma implementação abstrata que representa um intervalo de valores de um tipo genérico `T`. Ela define valores máximos, mínimos e atuais, fornecendo métodos utilitários adicionais para manipulação e cálculo de estados, como porcentagens e comparações.

***

#### Tipos Genéricos:

* **T**: Deve ser um tipo estruturado que implemente as interfaces `IComparable`, `IComparable<T>`, `IConvertible`, `IEquatable<T>` e `IFormattable`.

***

### Propriedades:

| Nome                | Tipo    | Descrição                                                               |
| ------------------- | ------- | ----------------------------------------------------------------------- |
| `Percentage`        | `float` | Retorna a porcentagem do valor atual em relação ao máximo. _(Abstrato)_ |
| `InversePercentage` | `float` | Retorna o complemento da porcentagem atual. _(Abstrato)_                |
| `IsFull`            | `bool`  | Indica se o valor atual é igual ou maior que o máximo. _(Abstrato)_     |
| `HasValue`          | `bool`  | Indica se o valor atual é maior que 0. _(Abstrato)_                     |
| `IsZero`            | `bool`  | Indica se o valor atual é 0. _(Abstrato)_                               |
| `MissingValue`      | `T`     | Retorna o valor que falta para atingir o máximo. _(Abstrato)_           |
| `MaxValue`          | `T`     | Define ou obtém o valor máximo do intervalo.                            |
| `MinValue`          | `T`     | Define ou obtém o valor mínimo do intervalo.                            |
| `CurrentValue`      | `T`     | Define ou obtém o valor atual do intervalo. _(Abstrato)_                |

***

### Construtores:

| Nome           | Descrição                        |
| -------------- | -------------------------------- |
| `ValueRange()` | Construtor padrão que inicializa |

um intervalo vazio com valores padrão. | | `ValueRange(T maxValue, T currentValue, T minValue = default)` | Inicializa o intervalo com valores máximos, mínimos e atuais especificados. | | `ValueRange(ValueRange<T> other)` | Construtor de cópia que cria um intervalo baseado em outro já existente. |

***

### Eventos:

| Nome             | Descrição                                                     |
| ---------------- | ------------------------------------------------------------- |
| `OnValueChanged` | Evento acionado quando o valor atual do intervalo é alterado. |

***

### Métodos Públicos:

| Nome                                 | Retorno  | Descrição                                                                                   |
| ------------------------------------ | -------- | ------------------------------------------------------------------------------------------- |
| `SetToMaxValue()`                    | `void`   | Define o valor atual como o valor máximo do intervalo.                                      |
| `SetToMinValue()`                    | `void`   | Define o valor atual como o valor mínimo do intervalo.                                      |
| `SetToPercentage(float percentage)`  | `void`   | Define o valor atual baseado na porcentagem especificada. _(Abstrato)_                      |
| `ToFormattedText()`                  | `string` | Retorna uma string formatada com o valor atual e o valor máximo, no formato `Atual/Máximo`. |
| `CompareTo(ValueRange<T> other)`     | `int`    | Compara o intervalo atual com outro, retornando -1, 0 ou 1 para menor, igual ou maior.      |
| `IsGreaterThan(ValueRange<T> other)` | `bool`   | Retorna `true` se o valor atual do intervalo for maior que o de outro intervalo.            |
| `IsLessThan(ValueRange<T> other)`    | `bool`   | Retorna `true` se o valor atual do intervalo for menor que o de outro intervalo.            |

***

### Métodos Protegidos:

| Nome           | Retorno | Descrição                                                                       |
| -------------- | ------- | ------------------------------------------------------------------------------- |
| `CallEvents()` | `void`  | Invoca o evento `OnValueChanged` para notificar que o valor atual foi alterado. |
