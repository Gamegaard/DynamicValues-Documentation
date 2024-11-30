# IntModifierApplier\<TCaster>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe abstrata `IntModifierApplier<TCaster>` estende `ModifierApplier<Modifier<int>, TCaster, int>` e fornece uma base para aplicar modificadores inteiros (`int`) a um tipo específico de objeto receptor (`TCaster`). Suporta modificadores permanentes e temporários.

***

### Propriedades Herdadas:

| Nome                  | Tipo                      | Descrição                                                                    |
| --------------------- | ------------------------- | ---------------------------------------------------------------------------- |
| `ModfierType`         | `ModifierCalculationType` | Tipo de cálculo aplicado pelo modificador.                                   |
| `Value`               | `int`                     | O valor aplicado pelo modificador.                                           |
| `DurationInSeconds`   | `float`                   | Duração do modificador em segundos. Use `0` para efeitos permanentes.        |
| `CalculationStrategy` | `ModifierStrategy<int>`   | A estratégia de cálculo usada para modificadores customizados, se aplicável. |

***

### Métodos Públicos:

| Nome                                                                 | Retorno         | Descrição                                                                                                  |
| -------------------------------------------------------------------- | --------------- | ---------------------------------------------------------------------------------------------------------- |
| `CreateModifierInstance(object source, float durationInSeconds = 0)` | `Modifier<int>` | Cria uma instância do modificador, retornando um modificador permanente ou temporário com base na duração. |

***

### Construtores:

| Nome                            | Descrição                                  |
| ------------------------------- | ------------------------------------------ |
| `IntModifierApplier<TCaster>()` | Construtor padrão que inicializa a classe. |

***
