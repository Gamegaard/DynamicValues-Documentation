---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Guia de Uso

## **1. Introdução**

Este sistema é uma solução robusta para gerenciar valores dinâmicos e modificadores em jogos. Ele oferece:

* **DynamicValue**: Representa valores dinâmicos básicos.
* **DynamicFloat/DynamicInt**: Extensões para valores `float` e `int`.
* **Modifiers**: Aplicam mudanças a valores dinâmicos.
* **TemporaryModifiers**: Buffs ou debuffs com duração limitada.
* **MultipleModifierApplier**: Aplica vários modificadores simultaneamente.

Este guia cobre:

* Trabalhando com valores dinâmicos e modificadores.
* Criando modificadores personalizados.
* Usando `MultipleModifierApplier` para simplificar modificações complexas.
* Exemplo de uso de valores mais simples, como o FloatRange.

***

## **2. Trabalhando com Valores Dinâmicos**

### **2.1 Valores Básicos**

Para gerenciar valores dinâmicos sem modificadores, use `DynamicFloat` ou `DynamicInt`:

```csharp
public class Player : MonoBehaviour
{
    public DynamicFloat Health = new DynamicFloat(100f);

    void Start()
    {
        Debug.Log($"Vida inicial: {Health.FinalValue}");
        Health.BaseValue += 20;
        Debug.Log($"Vida após aumento: {Health.FinalValue}");
    }
}
```

### **2.2 Adicionando Modificadores**

Adicione modificadores para alterar os valores dinamicamente:

```csharp
public class Player : MonoBehaviour
{
    public DynamicFloat AttackPower = new DynamicFloat(50f);

    void Start()
    {
        // Adiciona um modificador plano (+10).
        AttackPower.AddModifier(new FloatModifier(ModifierCalculationType.Flat, 10f, this));

        // Adiciona um modificador percentual (+20%).
        AttackPower.AddModifier(new FloatModifier(ModifierCalculationType.Percentage, 20f, this));

        Debug.Log($"Poder de Ataque: {AttackPower.FinalValue}"); // Saída: 72 (50 + 10 + 20%)
    }
}
```

***

## **3. Usando Modificadores Temporários**

Modificadores temporários podem adicionar buffs ou debuffs com duração limitada:

```csharp
public class BuffExample : MonoBehaviour
{
    public DynamicFloat Speed = new DynamicFloat(10f);

    void Start()
    {
        // Buff temporário de velocidade (+5) por 10 segundos.
        Speed.AddModifier(new TemporaryFloatModifier(ModifierCalculationType.Flat, 5f, 10f, this));

        Debug.Log($"Velocidade inicial: {Speed.FinalValue}"); // Saída: 15
        Invoke(nameof(CheckSpeed), 11f); // Verifica após 11 segundos.
    }

    void CheckSpeed()
    {
        Debug.Log($"Velocidade após expiração: {Speed.FinalValue}"); // Saída: 10
    }
}
```

***

## **4. Usando `MultipleModifierApplier`**

O `MultipleModifierApplier` aplica múltiplos modificadores simultaneamente. Ideal para buffs complexos ou configurações automáticas.

#### **Exemplo: Buff de Equipamento**

```csharp
public class EquipmentExample : MonoBehaviour
{
    [SerializeField] private MultipleModifierApplier<Player> equipmentModifiers;
    [SerializeField] private Player player;

    void Start()
    {
        // Configurar os modificadores no Editor Unity.
        equipmentModifiers.Apply(player);
        Debug.Log($"Vida com equipamento: {player.Health.FinalValue}");
    }
}
```

***

## **5. Criando Modificadores Customizados**

### **5.1 Estratégia Customizada**

Crie uma estratégia para cálculos personalizados:

```csharp
public class RandomModifierStrategy : ModifierStrategy<float>
{
    public override float Apply(float baseValue, float modifierValue)
    {
        return UnityEngine.Random.Range(0, modifierValue);
    }
}
```

### **5.2 Usando o Modificador Customizado**

```csharp
public class CustomModifierExample : MonoBehaviour
{
    public DynamicFloat Luck = new DynamicFloat(10f);

    void Start()
    {
        Luck.AddModifier(new FloatModifier(ModifierCalculationType.Custom, 5f, this, new RandomModifierStrategy()));
        Debug.Log($"Sorte com modificador: {Luck.FinalValue}");
    }
}
```

***

## **6. Explicação do Enum `ModifierCalculationType`**

O enum `ModifierCalculationType` define como o modificador afeta o valor:

* **Flat**: Adiciona um valor fixo ao base (`10f` → `20f`).
* **Percentage**: Aplica uma porcentagem ao valor base (`10f` + `50%` → `15f`).
* **PercentageOverAll**: Calcula sobre o valor final, incluindo outros modificadores.
* **PercentageOverAllFlat**: Calcula porcentagens sobre valores base somados a modificadores planos.
* **Custom**: Usa uma estratégia personalizada para cálculos.

## **7. Usando Valores Simples (Sem Modificadores)**

O sistema também oferece **versões simplificadas** de atributos dinâmicos, como `FloatRange`, `IntRange` e suas variações. Esses valores não possuem suporte direto ao sistema de modificadores, mas permitem lógica personalizada e mais controle por parte do desenvolvedor. Isso é ideal para cenários em que:

* A complexidade dos modificadores não é necessária.
* O desenvolvedor deseja aplicar mudanças diretamente nos valores.
* É importante minimizar o custo de desempenho, utilizando estruturas mais leves.

```csharp
public class SimpleValueExample : MonoBehaviour 
{ 
    [SerializeField] private FloatRange health = new FloatRange(0, 100);
    
    void Start()
    {
        Debug.Log($"Vida Inicial: {health.MaxValue}"); // Saída: 100
    
        // Reduzindo a vida diretamente
        health.MaxValue -= 10;
        Debug.Log($"Vida Após Dano: {health.MaxValue}"); // Saída: 90
    }
}
```

#### **Diferenças Principais Entre `DynamicValue` e Valores Simples**

| Característica              | `DynamicValue`                                      | `FloatRange` / Simples          |
| --------------------------- | --------------------------------------------------- | ------------------------------- |
| **Suporte a Modificadores** | Sim (inclui temporários, percentuais, customizados) | Não                             |
| **Controle Direto**         | Através de métodos (`AddModifier`)                  | Direto nos valores (`MaxValue`) |
| **Custo de Desempenho**     | Maior devido ao gerenciamento dinâmico              | Menor, mais leve                |
| **Facilidade de Uso**       | Mais automatizado                                   | Mais manual                     |

***

#### **Quando Usar Cada Abordagem**

* **Use `DynamicValue`:** Quando o sistema precisa gerenciar modificadores dinâmicos automaticamente e é necessário rastrear suas origens, durações e tipos de cálculo.
* **Use Valores Simples (`FloatRange`):** Para lógicas simples ou personalizadas, em que a sobrecarga do sistema de modificadores não é necessária.

***

#### **Exemplo com `FloatRange`**

O `FloatRange` representa um intervalo entre dois valores (`MinValue` e `MaxValue`) sem modificadores aplicados. Você pode manipular esses valores diretamente.

```csharp
csharpCopiar códigousing UnityEngine;

public class SimpleValueExample : MonoBehaviour
{
    [SerializeField] private FloatRange health = new FloatRange(0, 100);

    void Start()
    {
        Debug.Log($"Vida Inicial: {health.MaxValue}"); // Saída: 100

        // Reduzindo a vida diretamente
        health.MaxValue -= 10;
        Debug.Log($"Vida Após Dano: {health.MaxValue}"); // Saída: 90
    }
}
```

***

## **8. Gerenciamento de Atributos Complexos**

Combine diferentes tipos de valores e modificadores para cenários avançados:

* Buffs cumulativos.
* Sistemas de energia ou mana com decaimento ao longo do tempo.
* Modificadores baseados em condições, como “aumentar dano se a vida for baixa”.

***

## **9. Boas Práticas**

1.  **Atualização de Modificadores**: Certifique-se de chamar `UpdateTempModifiers()` para modificadores temporários:

    ```csharp
    void Update()
    {
        health.UpdateTempModifiers();
    }
    ```
2. **Centralize o Controle**: Use controladores para organizar e atualizar múltiplos atributos.
3. **Otimize Estratégias**: Reutilize estratégias personalizadas em diferentes atributos.
4. **Use o Editor Unity**: Configure modificadores e atributos no Editor Unity para facilitar ajustes rápidos sem mexer em código.

***
