---
icon: file
---

# DynamicTimedIntRangeWithCurve

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `DynamicTimedIntRangeWithCurve` estende `DynamicTimedIntRange`, adicionando uma curva de animação (`AnimationCurve`) para ajustar dinamicamente as alterações de valores inteiros ao longo do tempo com base em um temporizador.

***

### Propriedades:

| Nome         | Tipo             | Descrição                                                     |
| ------------ | ---------------- | ------------------------------------------------------------- |
| `ValueCurve` | `AnimationCurve` | Curva que controla como o valor é ajustado ao longo do tempo. |

***

### Construtores:

| Nome                                                                                                                                                                           | Descrição                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `DynamicTimedIntRangeWithCurve()`                                                                                                                                              | Construtor padrão que inicializa a classe com valores padrão.                                          |
| `DynamicTimedIntRangeWithCurve(int baseValue, int currentValue, int changeBaseValue, float changeTime, AnimationCurve valueCurve, bool isPaused = false, float timeScale = 1)` | Inicializa a classe com valores base, valores atuais, alterações base, intervalo de tempo e uma curva. |
| `DynamicTimedIntRangeWithCurve(DynamicTimedIntRangeWithCurve other)`                                                                                                           | Construtor de cópia que cria uma nova instância com base em outra existente.                           |

***

### Métodos Públicos:

| Nome                   | Retorno  | Descrição                                                                                                    |
| ---------------------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| `UpdateChangedValue()` | `bool`   | Atualiza o valor atual com base no temporizador e na curva de valor. Retorna `true` se o valor foi alterado. |
| `ToString()`           | `string` | Retorna uma representação em texto do estado atual, incluindo a avaliação da curva de animação.              |

***
