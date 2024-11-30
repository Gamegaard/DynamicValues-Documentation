---
icon: file
---

# DynamicTimedIntRange

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `DynamicTimedIntRange` estende `DynamicIntRange`, adicionando funcionalidades de modificação de valores ao longo do tempo com base em um temporizador. É ideal para valores dinâmicos como atributos de jogos que se regeneram, decaem ou mudam periodicamente.

***

### Propriedades:

| Nome                 | Tipo                  | Descrição                                                                             |
| -------------------- | --------------------- | ------------------------------------------------------------------------------------- |
| `ValueShift`         | `DynamicIntRange`     | Representa o intervalo dinâmico que altera o valor atual ao longo do tempo.           |
| `ValueShiftTimer`    | `FreezeableLoopTimer` | Temporizador que controla o intervalo das mudanças de valor e lida com congelamentos. |
| `IsValueShiftPaused` | `bool`                | Indica se as alterações de valor estão pausadas.                                      |
| `ChangeTime`         | `float`               | O intervalo de tempo em que o valor deve mudar.                                       |
| `TimeScale`          | `float`               | Escala de tempo aplicada ao temporizador de alterações de valor.                      |

***

### Construtores:

| Nome                                                                                                                                       | Descrição                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| `DynamicTimedIntRange()`                                                                                                                   | Construtor padrão que inicializa a classe com valores padrão.                                      |
| `DynamicTimedIntRange(int baseValue, int currentValue, int changeBaseValue, float changeTime, bool isPaused = false, float timeScale = 1)` | Inicializa a classe com valores base, atuais, alterações base e intervalo de tempo personalizados. |
| `DynamicTimedIntRange(int baseValue, int changeBaseValue, float changeTime, bool isPaused = false, float timeScale = 1)`                   | Inicializa a classe com valores base e alterações base para mudanças periódicas.                   |
| `DynamicTimedIntRange(DynamicTimedIntRange other)`                                                                                         | Construtor de cópia que cria uma nova instância com base em outra existente.                       |

***

### Métodos Públicos:

| Nome                            | Retorno  | Descrição                                                                                                              |
| ------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------- |
| `UpdateAll()`                   | `void`   | Atualiza todos os comportamentos dinâmicos, incluindo modificadores temporários e alterações baseadas no temporizador. |
| `UpdateChangedValue()`          | `bool`   | Atualiza o valor atual com base no temporizador e nas alterações de valor. Retorna `true` se o valor foi alterado.     |
| `Freeze(float timeInSeconds)`   | `void`   | Congela as alterações de valor por uma duração especificada em segundos.                                               |
| `Unfreeze()`                    | `void`   | Descongela as alterações de valor, permitindo que continuem ao longo do tempo.                                         |
| `Pause()`                       | `void`   | Pausa as alterações de valor, impedindo mudanças até que sejam retomadas.                                              |
| `Unpause()`                     | `void`   | Retoma as alterações de valor, permitindo que o temporizador funcione novamente.                                       |
| `ResetValueShiftTimer()`        | `void`   | Reseta o temporizador de alterações de valor.                                                                          |
| `SetTimeScale(float timeScale)` | `void`   | Define uma nova escala de tempo para o temporizador de alterações de valor.                                            |
| `ToString()`                    | `string` | Retorna uma representação em texto do estado atual da classe, incluindo valores e configurações do temporizador.       |

***
