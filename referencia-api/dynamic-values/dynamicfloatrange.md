---
icon: file
---

# DynamicFloatRange

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `DynamicFloatRange` estende `DynamicFloat` e implementa a interface `INumberRange<float>`, adicionando funcionalidades específicas de intervalos. Permite manipulação dinâmica de valores de ponto flutuante com operações baseadas em intervalos e suporte a eventos de mudança de valor.

***

### Propriedades:

| Nome                | Tipo    | Descrição                                                 |
| ------------------- | ------- | --------------------------------------------------------- |
| `CurrentValue`      | `float` | O valor atual dentro do intervalo.                        |
| `MaxValue`          | `float` | O valor máximo do intervalo.                              |
| `MinValue`          | `float` | O valor mínimo do intervalo.                              |
| `Percentage`        | `float` | A porcentagem do valor atual em relação ao máximo.        |
| `InversePercentage` | `float` | O complemento da porcentagem atual (1 - Percentage).      |
| `IsFull`            | `bool`  | Indica se o valor atual é maior ou igual ao máximo.       |
| `HasValue`          | `bool`  | Indica se o valor atual é maior que 0.                    |
| `IsZero`            | `bool`  | Indica se o valor atual é igual a 0.                      |
| `MissingValue`      | `float` | Retorna a diferença entre o valor atual e o valor máximo. |

***

### Construtores:

| Nome                                                     | Descrição                                                                  |
| -------------------------------------------------------- | -------------------------------------------------------------------------- |
| `DynamicFloatRange()`                                    | Construtor padrão que inicializa o intervalo com valores padrão.           |
| `DynamicFloatRange(float baseValue)`                     | Inicializa o intervalo com um valor base especificado.                     |
| `DynamicFloatRange(float baseValue, float currentValue)` | Inicializa o intervalo com valores base e atual especificados.             |
| `DynamicFloatRange(DynamicFloatRange other)`             | Construtor de cópia que cria um novo intervalo baseado em outro existente. |

***

### Métodos Públicos:

| Nome                                | Retorno  | Descrição                                                                                  |
| ----------------------------------- | -------- | ------------------------------------------------------------------------------------------ |
| `SetToMaxValue()`                   | `void`   | Define o valor atual como o valor máximo do intervalo.                                     |
| `SetToMinValue()`                   | `void`   | Define o valor atual como o valor mínimo do intervalo.                                     |
| `SetToPercentage(float percentage)` | `void`   | Define o valor atual com base em uma porcentagem do intervalo.                             |
| `ToString()`                        | `string` | Retorna uma representação em texto do estado atual do intervalo no formato `Atual/Máximo`. |

***

### Eventos:

| Nome                    | Descrição                                            |
| ----------------------- | ---------------------------------------------------- |
| `OnCurrentValueChanged` | Evento acionado sempre que o valor atual é alterado. |

***

### Operadores:

| Operador                    | Descrição                                                                                   |
| --------------------------- | ------------------------------------------------------------------------------------------- |
| `explicit operator int`     | Converte o valor atual para um `int`.                                                       |
| `explicit operator long`    | Converte o valor atual para um `long`.                                                      |
| `explicit operator float`   | Converte o valor atual para um `float`.                                                     |
| `explicit operator double`  | Converte o valor atual para um `double`.                                                    |
| `explicit operator decimal` | Converte o valor atual para um `decimal`.                                                   |
| `++` / `--`                 | Incrementa ou decrementa o valor atual em 1.                                                |
| `+`, `-`, `*`, `/`          | Realiza operações matemáticas entre `DynamicFloatRange` e valores do tipo `int` ou `float`. |

***
