---
icon: file
---

# FloatRange

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `FloatRange` representa um intervalo de valores do tipo `float`, com métodos utilitários para gerenciar e calcular valores dentro do intervalo. É uma implementação concreta de `ValueRange<float>`.

***

### Propriedades:

| Nome                | Tipo    | Descrição                                                                                               |
| ------------------- | ------- | ------------------------------------------------------------------------------------------------------- |
| `Percentage`        | `float` | Retorna a porcentagem do valor atual em relação ao máximo.                                              |
| `InversePercentage` | `float` | Retorna o complemento da porcentagem atual (1 - Percentage).                                            |
| `IsFull`            | `bool`  | Indica se o valor atual é maior ou igual ao máximo.                                                     |
| `HasValue`          | `bool`  | Indica se o valor atual é maior que 0.                                                                  |
| `IsZero`            | `bool`  | Indica se o valor atual é igual a 0.                                                                    |
| `MissingValue`      | `float` | Calcula a diferença entre o valor máximo e o valor atual.                                               |
| `CurrentValue`      | `float` | Define ou obtém o valor atual do intervalo, garantindo que esteja dentro dos limites mínimos e máximos. |

***

### Construtores:

| Nome                                                                 | Descrição                                                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `FloatRange()`                                                       | Construtor padrão que inicializa o intervalo com o valor máximo definido como `float.MaxValue`.    |
| `FloatRange(ValueRange<float> other)`                                | Construtor de cópia que cria um intervalo com base em outro intervalo de tipo `ValueRange<float>`. |
| `FloatRange(float maxValue, float currentValue, float minValue = 0)` | Inicializa o intervalo com valores máximos, mínimos e atuais especificados.                        |

***

### Métodos Públicos:

| Nome                                | Retorno | Descrição                                                                                            |
| ----------------------------------- | ------- | ---------------------------------------------------------------------------------------------------- |
| `SetToPercentage(float percentage)` | `void`  | Define o valor atual com base na porcentagem fornecida, calculando em relação ao intervalo definido. |

***

Esta documentação segue o padrão solicitado e está pronta para ser incluída em um sistema como GitBook. Se precisar de mais modificações ou exemplos de uso, é só avisar!
