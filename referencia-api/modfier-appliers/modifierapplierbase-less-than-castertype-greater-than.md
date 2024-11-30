# ModifierApplierBase\<CasterType>

Descrição:

A classe abstrata genérica `ModifierApplierBase<CasterType>` estende `ModifierApplierBase` e implementa a interface `IModifierApplier<CasterType>`. Ela serve como uma base para aplicadores de modificadores, permitindo sua serialização no Unity, que possui limitações quanto a interfaces.

***

### Métodos Abstratos:

| Nome                           | Retorno | Descrição                                                             |
| ------------------------------ | ------- | --------------------------------------------------------------------- |
| `Apply(CasterType caster)`     | `void`  | Aplica o modificador ao objeto do tipo especificado.                  |
| `Remove(CasterType caster)`    | `void`  | Remove o modificador do objeto do tipo especificado.                  |
| `CanAffect(CasterType caster)` | `bool`  | Determina se o modificador pode afetar o objeto do tipo especificado. |

***

### Construtores:

| Nome                                | Descrição                                       |
| ----------------------------------- | ----------------------------------------------- |
| `ModifierApplierBase<CasterType>()` | Construtor padrão que inicializa a classe base. |

***
