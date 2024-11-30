# DynamicValue\<TValue>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe abstrata `DynamicValue<ValueType>` representa um valor dinâmico que pode ser modificado por modificadores permanentes e temporários, com suporte para eventos baseados em alterações e atualizações automáticas.

***

### Propriedades:

| Nome                   | Tipo        | Descrição                                                                                                    |
| ---------------------- | ----------- | ------------------------------------------------------------------------------------------------------------ |
| `MaximumValue`         | `ValueType` | O valor máximo possível após aplicar todos os modificadores positivos. _(Abstrato)_                          |
| `MinimumValue`         | `ValueType` | O valor mínimo possível após aplicar todos os modificadores negativos. _(Abstrato)_                          |
| `HasAnyModification`   | `bool`      | Indica se há algum modificador aplicado (permanente ou temporário).                                          |
| `HasConstModification` | `bool`      | Indica se há modificadores permanentes aplicados.                                                            |
| `HasTempModification`  | `bool`      | Indica se há modificadores temporários aplicados.                                                            |
| `TempModifierCount`    | `int`       | Retorna a quantidade de modificadores temporários aplicados.                                                 |
| `StaticModifierCount`  | `int`       | Retorna a quantidade de modificadores permanentes aplicados.                                                 |
| `AllModifiersCount`    | `int`       | Retorna a quantidade total de modificadores aplicados (permanentes e temporários).                           |
| `BaseValue`            | `ValueType` | O valor base sem modificadores.                                                                              |
| `FinalValue`           | `ValueType` | O valor final calculado após aplicar todos os modificadores. Recalcula automaticamente se marcado como sujo. |
| `IsDirty`              | `bool`      | Indica se o valor precisa ser recalculado.                                                                   |

***

### Construtores:

| Nome                                | Descrição                                                                             |
| ----------------------------------- | ------------------------------------------------------------------------------------- |
| `DynamicValue()`                    | Construtor padrão que inicializa o valor dinâmico com listas vazias de modificadores. |
| `DynamicValue(ValueType baseValue)` | Inicializa o valor dinâmico com um valor base especificado.                           |

***

### Métodos Públicos:

| Nome                                                                          | Retorno     | Descrição                                                                     |
| ----------------------------------------------------------------------------- | ----------- | ----------------------------------------------------------------------------- |
| `UpdateTempModifiers()`                                                       | `void`      | Atualiza os modificadores temporários, removendo aqueles que expiraram.       |
| `ChangeBaseValue(ValueType newValue)`                                         | `void`      | Altera o valor base e marca o valor como sujo.                                |
| `CallEvents()`                                                                | `void`      | Aciona o evento de alteração do valor.                                        |
| `AddModifier(Modifier<ValueType> modifier)`                                   | `void`      | Adiciona um novo modificador ao valor.                                        |
| `AddModifier(IEnumerable<Modifier<ValueType>> modifiers)`                     | `void`      | Adiciona uma coleção de modificadores ao valor.                               |
| `RemoveModifier(Modifier<ValueType> modifier)`                                | `bool`      | Remove um modificador específico do valor.                                    |
| `RemoveAllModifierFromSource(object source)`                                  | `bool`      | Remove todos os modificadores permanentes de uma fonte específica.            |
| `RemoveTempModifier(TemporaryModifier<ValueType> modifier)`                   | `bool`      | Remove um modificador temporário específico do valor.                         |
| `RemoveAllTempModifierFromSource(object source)`                              | `bool`      | Remove todos os modificadores temporários de uma fonte específica.            |
| `ForceDirtyCalculation()`                                                     | `void`      | Recalcula o valor final se estiver marcado como sujo.                         |
| `PreviewModfierValue(Modifier<ValueType> modifier)`                           | `ValueType` | Calcula o valor de um modificador sem aplicá-lo permanentemente.              |
| `PreviewModifierResult(IEnumerable<Modifier<ValueType>> modifiers)`           | `ValueType` | Calcula o valor resultante após aplicar uma coleção de modificadores.         |
| `PreviewModifierResult(Modifier<ValueType> modifier)`                         | `ValueType` | Calcula o valor resultante após aplicar um modificador específico.            |
| `AbsorbModifiersIntoBaseValue(Func<Modifier<ValueType>, bool> filter = null)` | `void`      | Move todos os modificadores filtrados para o valor base e os remove da lista. |

***

### Métodos Protegidos:

| Nome                                                                                                  | Retorno     | Descrição                                                                         |
| ----------------------------------------------------------------------------------------------------- | ----------- | --------------------------------------------------------------------------------- |
| `CalculateFinalValue<H>(List<TemporaryModifier<ValueType>> tempMods, List<Modifier<ValueType>> mods)` | `ValueType` | Calcula o valor final considerando todos os modificadores aplicados. _(Abstrato)_ |
| `GetAllFlat()`                                                                                        | `ValueType` | Obtém o valor total de modificadores do tipo flat. _(Abstrato)_                   |
| `SumValueWithMode(ValueType value, Modifier<ValueType> mod)`                                          | `ValueType` | Soma um modificador ao valor base. _(Abstrato)_                                   |
| `SubtractValues(ValueType value1, ValueType value2)`                                                  | `ValueType` | Subtrai dois valores do tipo `ValueType`. _(Abstrato)_                            |
| `NormalizedValue(float value)`                                                                        | `float`     | Normaliza um valor dividindo-o por 100.                                           |

***

### Eventos:

| Nome             | Descrição                                  |
| ---------------- | ------------------------------------------ |
| `OnValueChanged` | Evento acionado quando o valor é alterado. |

***
