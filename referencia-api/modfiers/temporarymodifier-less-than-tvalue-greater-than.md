# TemporaryModifier\<TValue>

Namespace:

**Gamegaard.DynamicValues**

***

#### Descrição:

A classe abstrata genérica `TemporaryModifier<TValue>` estende `Modifier<TValue>` e representa um modificador temporário que expira após uma duração especificada. Integra-se com um temporizador para rastrear o tempo restante e oferece suporte a pausas e reinicializações.

***

### Propriedades:

| Nome                | Tipo    | Descrição                                                         |
| ------------------- | ------- | ----------------------------------------------------------------- |
| `HasFinished`       | `bool`  | Indica se a duração do modificador foi concluída.                 |
| `Percentage`        | `float` | Retorna o progresso do temporizador como uma porcentagem (0 a 1). |
| `DurationInSeconds` | `float` | Retorna a duração total do modificador em segundos.               |
| `IsPaused`          | `bool`  | Indica se o temporizador do modificador está pausado.             |

***

### Construtores:

| Nome                                                                                                                                                         | Descrição                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `TemporaryModifier(ModifierCalculationType type, TValue value, float durationInSeconds, object source, ModifierStrategy<TValue> calculationStrategy = null)` | Inicializa um novo modificador temporário com tipo de cálculo, valor base, duração e fonte associados. |

***

### Métodos Públicos:

| Nome                                | Retorno | Descrição                                                                                     |
| ----------------------------------- | ------- | --------------------------------------------------------------------------------------------- |
| `Update()`                          | `void`  | Atualiza o temporizador do modificador.                                                       |
| `CheckedUpdate()`                   | `bool`  | Atualiza o temporizador e retorna `true` se a duração foi concluída; caso contrário, `false`. |
| `Pause()`                           | `void`  | Pausa o temporizador do modificador.                                                          |
| `Resume()`                          | `void`  | Retoma o temporizador do modificador.                                                         |
| `ResetTimer()`                      | `void`  | Reseta o temporizador para o estado inicial com zero tempo decorrido.                         |
| `SetTimerTime(float timerDuration)` | `void`  | Define uma nova duração para o temporizador e reseta o tempo atual para zero.                 |

***
