---
icon: file
---

# FloatModifierApplier\<TCaster>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe abstrata `FloatModifierApplier<TCaster>` estende `ModifierApplier<Modifier<float>, TCaster, float>` e fornece uma base para aplicar modificadores de ponto flutuante (`float`) a um tipo específico de objeto receptor (`TCaster`). Suporta modificadores permanentes e temporários.

***

### Propriedades Herdadas:

| Nome                  | Tipo                      | Descrição                                                                    |
| --------------------- | ------------------------- | ---------------------------------------------------------------------------- |
| `ModfierType`         | `ModifierCalculationType` | Tipo de cálculo aplicado pelo modificador.                                   |
| `Value`               | `float`                   | O valor aplicado pelo modificador.                                           |
| `DurationInSeconds`   | `float`                   | Duração do modificador em segundos. Use `0` para efeitos permanentes.        |
| `CalculationStrategy` | `ModifierStrategy<float>` | A estratégia de cálculo usada para modificadores customizados, se aplicável. |

***

### Métodos Públicos:

| Nome                                                                 | Retorno           | Descrição                                                                                                  |
| -------------------------------------------------------------------- | ----------------- | ---------------------------------------------------------------------------------------------------------- |
| `GetDescription()`                                                   | `string`          | Retorna uma descrição do modificador.                                                                      |
| `CreateModifierInstance(object source, float durationInSeconds = 0)` | `Modifier<float>` | Cria uma instância do modificador, retornando um modificador permanente ou temporário com base na duração. |

***

### Construtores:

| Nome                              | Descrição                                  |
| --------------------------------- | ------------------------------------------ |
| `FloatModifierApplier<TCaster>()` | Construtor padrão que inicializa a classe. |

***
