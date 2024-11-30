---
icon: bolt
---

# Guia de Otimizações

Este guia visa fornecer práticas e dicas para maximizar a eficiência do sistema de modificadores, garantindo que ele funcione de forma eficaz em projetos com alta complexidade ou alto número de instâncias.

***

### **1. Escolha Estratégica de Tipos de Valores**

* **Use `DynamicValue` apenas quando necessário:**
  * `DynamicValue` e suas variações são projetados para suportar modificadores e estratégias complexas. Em atributos que não exigem modificadores dinâmicos, prefira valores mais simples como `FloatRange` ou `IntRange` ou números primitivos como int ou float.
* **Prefira `FloatRange` ou `IntRange` para lógica simples:**
  * Para casos onde o valor base, mínimo e máximo podem ser gerenciados diretamente sem modificadores, esses tipos são mais leves e performáticos.

***

### **2. Minimize Modificadores em Atributos de Atualização Contínua**

* **Evite modificadores em valores atualizados constantemente:**
  * Aplique modificadores temporários ou baseados em eventos apenas quando necessário.
  * Exemplo: Evite adicionar/remover modificadores no `Update` a cada frame.

***

### **3. Reutilização de Modificadores**

* **Reutilize instâncias de modificadores:**\
  Em vez de criar um novo modificador sempre, utilize um pool de objetos para reutilizar instâncias.\
  Isso é especialmente útil para modificadores temporários que expiram rapidamente.

***

### **4. Otimize Estratégias de Cálculo Customizadas**

* **Evite cálculos complexos desnecessários:**
  * Estratégias de cálculo, como `RandomCalculation`, devem ser otimizadas para evitar operações dispendiosas.
  * Use caches ou pré-calculações sempre que possível.
* **Use tipos nativos sempre que puder:**
  * Prefira cálculos diretos com floats, inteiros e suas variantes.

***

### **5. Controle a Frequência de Atualização**

* **Reduza o uso do `Update`:**
  * Atualize os valores apenas quando houver alterações significativas ou eventos relevantes.
  * Utilize eventos, como `OnValueChanged`, para recalcular valores quando necessário.
* **Use timers para valores temporários:**
  * Atualize modificadores temporários com timers ou corrotinas para evitar cálculos constantes.

***

### **6. Limpeza de Modificadores**

* **Remova modificadores inativos ou redundantes:**
  * Sempre remova modificadores de um atributo quando não forem mais necessários.
  * Use métodos como `RemoveAllModifiers()` após uma batalha ou evento para evitar acúmulo desnecessário.
* **Evite múltiplos modificadores com o mesmo efeito:**
  * Combine lógica sempre que possível para evitar redundância.

***

### **7. Use Configurações Apropriadas para Jogos de Alta Escala**

* **Gerencie modificadores com `MultipleModifierApplier`:**
  * Utilize esta classe para aplicar e gerenciar grupos de modificadores de forma eficiente, especialmente em personagens com múltiplos buffs/debuffs.
* **Divida atributos por relevância:**
  * Atributos raramente modificados podem ser armazenados como valores simples (`FloatRange`), enquanto atributos dinâmicos mais frequentemente modificados podem usar `DynamicValue`.

***

### **8. Profiling e Testes de Performance**

* **Use o Profiler do Unity:**
  * Monitore o impacto do sistema no desempenho, especialmente em cenas com muitos objetos usando modificadores.
* **Teste com diferentes quantidades de instâncias:**
  * Simule cenários de pior caso, como 100+ inimigos ativos com atributos dinâmicos.

***

### **9. Evite Garbage Collection Excessiva**

* **Evite criar listas ou arrays temporários:**
  * Sempre que possível, trabalhe com referências diretas em vez de criar objetos temporários.

***

### **10. Organize Modificadores Customizados**

* **Centralize cálculos customizados em classes dedicadas:**
  * Mantenha estratégias de cálculo customizadas em classes separadas e reutilizáveis.
* **Limite a complexidade dos cálculos:**
  * Estratégias muito complicadas podem impactar o desempenho, especialmente em valores atualizados frequentemente.

***
