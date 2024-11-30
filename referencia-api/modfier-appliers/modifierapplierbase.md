---
icon: file
---

# ModifierApplierBase

Namespace:

**Global**

***

#### Descrição:

A classe `ModifierApplierBase` é uma classe base serializável que fornece funcionalidades básicas para aplicadores de modificadores. Inclui suporte para descrições e ferramentas adicionais para organização no editor Unity.

***

### Propriedades (Editor-Only):

| Nome   | Tipo     | Descrição                                                                                            |
| ------ | -------- | ---------------------------------------------------------------------------------------------------- |
| `Name` | `string` | (Somente no Editor Unity) Permite exibir o nome do modificador no Inspector para melhor organização. |

***

### Métodos Públicos:

| Nome               | Retorno  | Descrição                                                                          |
| ------------------ | -------- | ---------------------------------------------------------------------------------- |
| `GetDescription()` | `string` | Retorna uma descrição padrão da classe. Pode ser sobrescrita em classes derivadas. |

***

### Construtores:

| Nome                    | Descrição                                       |
| ----------------------- | ----------------------------------------------- |
| `ModifierApplierBase()` | Construtor padrão que inicializa a classe base. |

***
