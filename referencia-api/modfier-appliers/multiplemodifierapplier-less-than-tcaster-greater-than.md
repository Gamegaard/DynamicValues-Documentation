---
icon: file
---

# MultipleModifierApplier\<TCaster>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `MultipleModifierApplier<TCaster>` gerencia e aplica múltiplos modificadores a um objeto receptor (`TCaster`). Suporta operações como adição, remoção e agregação de descrições, permitindo uma gestão centralizada de modificadores.

***

### Propriedades:

| Nome       | Tipo                                 | Descrição                                                             |
| ---------- | ------------------------------------ | --------------------------------------------------------------------- |
| `Modfiers` | `IReadOnlyList<ModifierApplierBase>` | Lista somente leitura dos modificadores gerenciados por este applier. |

***

### Construtores:

| Nome                        | Descrição                                                 |
| --------------------------- | --------------------------------------------------------- |
| `MultipleModifierApplier()` | Inicializa a classe com uma lista vazia de modificadores. |

***

### Métodos Públicos:

| Nome                                                      | Retorno               | Descrição                                                                                            |
| --------------------------------------------------------- | --------------------- | ---------------------------------------------------------------------------------------------------- |
| `AddModfier(ModifierApplierBase modifierApplierBase)`     | `void`                | Adiciona um modificador à lista gerenciada.                                                          |
| `RemoveModfier(ModifierApplierBase modifierApplierBase)`  | `bool`                | Remove o modificador especificado da lista. Retorna `true` se foi removido, caso contrário, `false`. |
| `ContaisModfier(ModifierApplierBase modifierApplierBase)` | `bool`                | Verifica se um modificador específico está na lista.                                                 |
| `GetRandom()`                                             | `ModifierApplierBase` | Retorna um modificador aleatório da lista.                                                           |
| `Apply(TCaster receiver)`                                 | `void`                | Aplica todos os modificadores gerenciados ao objeto receptor especificado.                           |
| `Remove(TCaster receiver)`                                | `void`                | Remove todos os modificadores do objeto receptor especificado.                                       |
| `CanAffect(TCaster receiver)`                             | `bool`                | Verifica se todos os modificadores podem afetar o receptor especificado.                             |
| `GetDescription()`                                        | `string`              | Retorna uma descrição concatenada de todos os modificadores gerenciados.                             |

***
