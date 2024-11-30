# IModifierApplier

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A interface `IModifierApplier<CasterType>` define métodos para aplicar, remover e verificar modificadores em objetos específicos, além de fornecer descrições sobre os modificadores.

***

### Métodos:

| Nome                             | Retorno  | Descrição                                                    |
| -------------------------------- | -------- | ------------------------------------------------------------ |
| `Apply(CasterType receiver)`     | `void`   | Aplica o modificador ao objeto especificado.                 |
| `Remove(CasterType receiver)`    | `void`   | Remove o modificador do objeto especificado.                 |
| `CanAffect(CasterType receiver)` | `bool`   | Verifica se o modificador pode afetar o objeto especificado. |
| `GetDescription()`               | `string` | Retorna uma descrição do modificador.                        |

***

## IModifierApplier\<CasterType, ValueType>

#### Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A interface `IModifierApplier<CasterType, ValueType>` estende `IModifierApplier<CasterType>` e adiciona uma propriedade de valor para modificadores baseados em números.

***

### Restrições de Tipo:

* **ValueType**: Deve ser um tipo estrutural que implemente as interfaces `IComparable`, `IConvertible`, `IEquatable`, e `IFormattable`.

***

### Propriedades:

| Nome    | Tipo        | Descrição                                         |
| ------- | ----------- | ------------------------------------------------- |
| `Value` | `ValueType` | Define ou obtém o valor associado ao modificador. |

***

### Métodos:

| Nome                             | Retorno  | Descrição                                                    |
| -------------------------------- | -------- | ------------------------------------------------------------ |
| `Apply(CasterType receiver)`     | `void`   | Aplica o modificador ao objeto especificado.                 |
| `Remove(CasterType receiver)`    | `void`   | Remove o modificador do objeto especificado.                 |
| `CanAffect(CasterType receiver)` | `bool`   | Verifica se o modificador pode afetar o objeto especificado. |
| `GetDescription()`               | `string` | Retorna uma descrição do modificador.                        |
