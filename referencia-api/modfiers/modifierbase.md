---
icon: file
---

# ModifierBase

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe abstrata `ModifierBase` serve como base para todos os modificadores de valor. Representa um modificador genérico com um tipo de cálculo e uma fonte associada, permitindo a extensão para diferentes tipos de valores.

***

### Propriedades:

| Nome       | Tipo                      | Descrição                                                                 |
| ---------- | ------------------------- | ------------------------------------------------------------------------- |
| `type`     | `ModifierCalculationType` | Tipo de cálculo aplicado pelo modificador.                                |
| `source`   | `object`                  | Objeto fonte associado ao modificador (ex.: item, habilidade, ou efeito). |
| `HasValue` | `bool`                    | Indica se o modificador possui um valor válido e não padrão. _(Abstrato)_ |

***

### Construtores:

| Nome                                                        | Descrição                                                                           |
| ----------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `ModifierBase(ModifierCalculationType type, object source)` | Inicializa uma nova instância da classe com o tipo de cálculo e a fonte associados. |

***

### Métodos Públicos:

| Nome         | Retorno  | Descrição                                                                  |
| ------------ | -------- | -------------------------------------------------------------------------- |
| `GetValue()` | `object` | Retorna o valor atual do modificador como um objeto genérico. _(Abstrato)_ |

***
