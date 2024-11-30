Segue a versão revisada para o documento **Instalação.md** com ícones e uma seção de extras no final:

```markdown
# 🚀 Instalação

---

## **1️⃣ Usando o Package Manager**

![Package Manager](https://img.shields.io/badge/Unity%20Package%20Manager-blue?style=flat-square)

1. Abra o Unity e vá para **`Window > Package Manager`**.
2. Clique no botão **`+`** no canto superior esquerdo e selecione **`Add package from git URL...`**.
3. Cole o seguinte link no campo de texto e clique em **`Add`**:
   ```
   https://github.com/Gamegaard/DynamicValues.git
   ```
4. O sistema será automaticamente adicionado ao projeto dentro da pasta **Packages**.

---

## **2️⃣ Baixando Diretamente**

![Download](https://img.shields.io/badge/Direct%20Download-green?style=flat-square)

1. Baixe o repositório diretamente como um arquivo `.zip` ou clone o projeto com o seguinte comando:
   ```bash
   git clone https://github.com/Gamegaard/DynamicValues.git
   ```
2. Extraia os arquivos (se necessário) e copie a pasta principal para o diretório **`Assets`** do seu projeto Unity.

---

## **⚙️ Configuração Pós-Instalação**

Após a instalação:

- **Verifique o Console do Unity:** Certifique-se de que não há erros ou conflitos.
- **Estrutura do Projeto:** Os scripts estarão disponíveis na pasta:
  ```
  Assets/Gamegaard/DynamicValues/
  ```
- **Configuração Inicial:** Consulte a seção [Guia de Início Rápido](./GettingStarted.md) para começar a configurar seus atributos dinâmicos.

---

## **📢 Extras**

### **Atualizações**
- **Pelo Package Manager:** Acesse o **Package Manager** e clique no botão **Update** ao lado do pacote.
- **Pelo Download Manual:** Baixe a versão mais recente do repositório e substitua os arquivos existentes no diretório **Assets**.

### **Requisitos**
- Unity **2020.3 LTS ou superior**.
- Suporte completo a **.NET Standard 2.1**.

### **Ajuda**
Se encontrar problemas:
- Consulte a [Seção de Troubleshooting](./Troubleshooting.md).
- Envie uma issue no [GitHub](https://github.com/Gamegaard/DynamicValues/issues).

---

Agora você está pronto para usar o **Sistema de Modificadores para Unity** no seu projeto! 🎉
```

Essa versão inclui ícones para identificar rapidamente os métodos de instalação e destaca os "Extras" para facilitar o entendimento. 

1. **Ícones adicionados:** Usando shields.io para visualmente destacar os métodos.
2. **Extras:** Requisitos, como lidar com problemas e links úteis.
3. **Configuração Pós-Instalação:** Orientações para garantir que tudo esteja funcionando corretamente.

Você pode copiar e usar diretamente no arquivo **`Installation.md`** do seu repositório de documentação.