---
icon: file
---

# ModifierCalculationType

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

O `ModifierCalculationType` é uma enumeração que define os tipos de cálculos que podem ser aplicados por um modificador em valores dinâmicos.

***

### Tipos de Cálculo:

| Tipo                    | Descrição                                                                                              |
| ----------------------- | ------------------------------------------------------------------------------------------------------ |
| `Flat`                  | Adiciona um valor fixo ao valor base.                                                                  |
| `BasePercentage`        | Aplica uma porcentagem com base no valor base.                                                         |
| `OverallPercentage`     | Aplica uma porcentagem com base no valor final calculado, incluindo todos os modificadores.            |
| `OverallFlatPercentage` | Aplica uma porcentagem na soma do valor base e dos modificadores fixos, ignorando outras porcentagens. |
| `Custom`                | Usa uma lógica ou estratégia personalizada para realizar o cálculo.                                    |

***
