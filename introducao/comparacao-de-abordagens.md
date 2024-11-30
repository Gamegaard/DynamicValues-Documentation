---
icon: scale-balanced
---

# Comparação de Abordagens

Nesta seção, comparamos três formas de gerenciar atributos dinâmicos em um sistema de regeneração de vida: **código manual**, **`TimedFloatRange`** e **`DynamicTimedFloatRange`**.

***

### **Código Nativo/Manual**

O método nativo requer a implementação manual de todos os aspectos relacionados à regeneração, como o valor atual, máximo e intervalo de regeneração.

```csharp
using UnityEngine;

public class Player : MonoBehaviour
{
    public float currentLife = 50f; // Vida atual
    public float maxLife = 100f; // Vida máxima
    public float regenerationRate = 5f; // Vida regenerada por segundo
    private float nextRegenTime = 0f; // Próximo momento para regenerar
    private float regenInterval = 1f; // Intervalo entre regenerações

    private void Update()
    {
        if (Time.time >= nextRegenTime)
        {
            nextRegenTime = Time.time + regenInterval;
            RegenerateLife();
        }

        // Evita que a vida exceda o máximo
        currentLife = Mathf.Clamp(currentLife, 0f, maxLife);

        Debug.Log($"Vida Atual: {currentLife}/{maxLife}");
    }

    private void RegenerateLife()
    {
        if (currentLife < maxLife)
        {
            currentLife += regenerationRate;
        }
    }
}
```

#### **Análise**

* **Prós:** Total controle sobre a lógica.
* **Contras:** Código extenso e repetitivo; difícil de manter e reutilizar; pouca escalabilidade.

***

### **Usando TimedFloatRange**

Com `TimedFloatRange`, parte da lógica de regeneração é automatizada, incluindo a atualização do valor atual baseado no tempo.

```csharp
using UnityEngine;
using Gamegaard.DynamicValues;

public class Player : MonoBehaviour
{
    [SerializeField]
    private TimedFloatRange life = new TimedFloatRange(50f, 100f, 5f, 1f); // Regenera 5 por segundo, atualiza a cada 1s

    private void Update()
    {
        life.UpdateChangedValue(); // Atualiza a regeneração automaticamente com base no tempo
        Debug.Log($"Vida Atual: {life.CurrentValue}/{life.MaxValue}");
    }
}
```

#### **Análise**

* **Prós:** Reduz a complexidade ao automatizar a lógica de regeneração.
* **Contras:** Não suporta modificadores diretamente; lógica mais simples que `DynamicTimedFloatRange`.

***

### **Usando DynamicTimedFloatRange**

Com `DynamicTimedFloatRange`, toda a lógica de regeneração e limites de valores é automatizada, incluindo suporte a modificadores.

```csharp
using UnityEngine;
using Gamegaard.DynamicValues;

public class Player : MonoBehaviour
{
    [SerializeField]
    private DynamicTimedFloatRange life = new DynamicTimedFloatRange(50f, 100f, 5f);

    private void Update()
    {
        life.UpdateChangedValue(); // Atualiza regeneração e modificadores automaticamente
        Debug.Log($"Vida Atual: {life.CurrentValue}/{life.MaxValue}");
    }
}
```

*   Adicione modificadores temporários diretamente:

    ```csharp
    life.AddModifier(new TemporaryFloatModifier(ModifierCalculationType.Flat, 10f, 10f, this));
    ```

#### **Análise**

* **Prós:** Simplicidade extrema, lógica integrada e suporte a modificadores.
* **Contras:** Depende do sistema de modificadores.

***

### **Comparação Direta**

| **Aspecto**                 | **Código Manual**    | **TimedFloatRange** | **DynamicTimedFloatRange** |
| --------------------------- | -------------------- | ------------------- | -------------------------- |
| **Linhas de Código**        | Extenso e repetitivo | Compacto            | Compacto                   |
| **Gerenciamento**           | Manual               | Automático          | Automático                 |
| **Reutilização**            | Baixa                | Alta                | Alta                       |
| **Suporte a Modificadores** | Manual               | Manual              | Integrado                  |
| **Complexidade**            | Alta                 | Moderada            | Baixa                      |
| **Flexibilidade**           | Limitada             | Alta                | Alta                       |
| **Manutenção**              | Difícil              | Moderada            | Fácil                      |
| **Performance**             | Alta                 | Média               | Menor                      |

***

### **Recomendações**

1. **Use Código Manual** para sistemas extremamente simples ou quando desejar controle total da lógica.
2. **Use TimedFloatRange** para simplificar lógicas de regeneração sem a necessidade de modificadores.
3. **Use DynamicTimedFloatRange** para automatizar lógicas complexas, especialmente quando buffs, debuffs e modificadores são requisitos.
