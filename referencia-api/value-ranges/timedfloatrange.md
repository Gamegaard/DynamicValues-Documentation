# TimedFloatRange

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe `TimedFloatRange` estende a funcionalidade de `FloatRange`, adicionando a capacidade de realizar alterações automáticas e cronometradas no valor atual do intervalo. É ideal para sistemas que exigem ajustes contínuos ao longo do tempo.

***

### Propriedades:

| Nome                 | Tipo                  | Descrição                                                                   |
| -------------------- | --------------------- | --------------------------------------------------------------------------- |
| `ValueShiftTimer`    | `FreezeableLoopTimer` | Timer que controla o intervalo entre alterações de valores.                 |
| `ValueShift`         | `FloatRange`          | Define a magnitude e o intervalo das alterações automáticas no valor atual. |
| `IsValueShiftPaused` | `bool`                | Indica se o processo de alteração de valores está pausado.                  |
| `ChangeTime`         | `float`               | Retorna a duração de cada ciclo de alteração de valor.                      |
| `TimeScale`          | `float`               | Retorna a escala de tempo aplicada ao timer, afetando sua velocidade.       |

***

### Construtores:

| Nome                                                                                                                                       | Descrição                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| `TimedFloatRange()`                                                                                                                        | Construtor padrão que inicializa a classe com valores padrão.                      |
| `TimedFloatRange(float maxValue, float currentValue, float changeBaseValue, float changeTime, bool isPaused = false, float timeScale = 1)` | Inicializa o intervalo com valores personalizados e configurações do timer.        |
| `TimedFloatRange(TimedFloatRange other)`                                                                                                   | Construtor de cópia que cria um novo intervalo baseado em uma instância existente. |

***

### Métodos Públicos:

| Nome                            | Retorno | Descrição                                                                                                                     |
| ------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `UpdateChangedValue()`          | `bool`  | Atualiza o valor atual aplicando a alteração, caso o timer tenha completado um ciclo. Retorna `true` se o valor foi alterado. |
| `Freeze(float timeInSeconds)`   | `void`  | Congela o timer por um período especificado em segundos.                                                                      |
| `Unfreeze()`                    | `void`  | Descongela o timer, permitindo que ele continue a contar.                                                                     |
| `Pause()`                       | `void`  | Pausa o processo de alteração de valores e o timer associado.                                                                 |
| `Unpause()`                     | `void`  | Retoma o processo de alteração de valores e o timer associado.                                                                |
| `SetTimeScale(float timeScale)` | `void`  | Define uma nova escala de tempo para o timer, ajustando a velocidade de suas contagens.                                       |

***

Esta documentação está formatada para fácil integração com sistemas como GitBook. Caso necessite de alterações ou adições, avise!
