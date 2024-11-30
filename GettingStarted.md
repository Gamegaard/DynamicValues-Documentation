# Guia Inicial

## Configuração Básica

Configure atributos dinâmicos no Unity para uso com o sistema de modificadores.

### Exemplo:

```csharp
public class Player : MonoBehaviour
{
    public DynamicValue<float> MaxLife = new DynamicValue<float>(100f);

    private void Start()
    {
        MaxLife.AddModifier(new FloatModifier(ModifierCalculationType.Flat, 50f, this));
        Debug.Log(MaxLife.FinalValue);
    }
}
```
