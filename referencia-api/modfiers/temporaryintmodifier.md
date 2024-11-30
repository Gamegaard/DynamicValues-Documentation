# TemporaryIntModifier

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `TemporaryIntModifier` estende `TemporaryModifier<int>` e representa um modificador temporário do tipo inteiro (`int`) que expira após uma duração especificada. É útil para efeitos temporários que alteram valores inteiros em sistemas dinâmicos.

***

### Propriedades:

| Nome       | Tipo   | Descrição                                                       |
| ---------- | ------ | --------------------------------------------------------------- |
| `HasValue` | `bool` | Indica se o modificador possui um valor base diferente de zero. |

***

### Construtores:

| Nome                                                                                                                                                      | Descrição                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `TemporaryIntModifier(ModifierCalculationType type, int value, float durationInSeconds, object source, ModifierStrategy<int> calculationStrategy = null)` | Inicializa um novo modificador temporário com tipo de cálculo, valor base, duração, fonte e estratégia opcional. |

***
