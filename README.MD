# Programação Orientada a Objetos (POO) 🚀

Este repositório é dedicado ao meu aprendizado sobre **Programação Orientada a Objetos (POO)**. Aqui, explico de forma simples e intuitiva os principais conceitos da POO com exemplos práticos em **Java**, utilizando apenas **animais de estimação** como exemplo para facilitar o entendimento.

# Classes e Objetos

Em **POO** (Programação Orientada a Objetos), classes são modelos que definem as características (**estado**) e comportamentos (**métodos**) de um objeto. Os objetos por sua vez são instâncias dessas classes, ou seja, representam entidades específicas baseadas no modelo definido pela classe.

### O que são **estados** e **métodos** de um objeto?

- **Estado**: Representa os atributos ou dados do objeto. São as informações que descrevem o objeto em um determinado momento.
- **Métodos**: Representa as ações ou métodos que o objeto pode executar, definindo como ele interage com outros objetos ou altera seu próprio estado.

### Analogias para facilitar o entendimento

Pense em uma classe como uma **receita de bolo**. A receita contém todos os ingredientes e instruções necessárias para fazer um bolo, mas por si só não é um bolo real. Já o bolo pronto é um **objeto**, ou seja, uma instância concreta daquela receita.

Outro exemplo: Imagine uma classe **"Animal"**. Essa classe define que todo animal tem um **nome** e uma **idade** (estado) e pode realizar ações como **exibir suas informações** (método).

Se tivermos um cachorro chamado **"Rex"**, ele seria um objeto da classe "Animal". Ele tem seu próprio nome e idade (estado) e pode realizar ações definidas na classe, como exibir suas informações (método). Outro cachorro chamado **"Bolt"** seria outro objeto da mesma classe, mas com um estado diferente.

### 📌 Exemplo Técnico:

```java
// Definição da classe Animal
class Animal {
    String nome; // Estado: nome do animal
    int idade;  // Estado: idade do animal

    // Método para exibir informações do animal
    void exibirInformacoes() {
        System.out.println("Nome: " + nome + ", Idade: " + idade + " anos");
    }
}

// Classe principal
public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Animal
        Animal pet = new Animal(); // Instância da classe "Animal"
        
        // Definindo o estado do objeto
        pet.nome = "Rex";
        pet.idade = 3;
        
        // Executando um método do objeto
        pet.exibirInformacoes();
    }
}
```

### 🔍 Explicação do Código:

1. Criamos a classe `Animal` com dois atributos: `nome` e `idade` (**estado**).
2. Definimos um método `exibirInformacoes()`, que exibe o nome e a idade do animal.
3. No método `main`, instanciamos um objeto `pet` da classe `Animal`.
4. Atribuímos valores ao estado do objeto (`nome` e `idade`).
5. Chamamos o método `exibirInformacoes()`, que imprime os detalhes do animal.

### 📌 Saída do Código:

```
Nome: Rex, Idade: 3 anos
```

Dessa forma, podemos entender claramente que os objetos têm um **estado** (valores específicos dos atributos) e um **comportamento** (métodos que definem suas ações).




---
# Encapsulamento

Em **POO** **encapsulamento** é um dos princípios fundamentais que protege os dados de um objeto, restringindo o acesso direto aos seus atributos e permitindo que sejam manipulados apenas através de métodos controlados.

Isso ajuda a manter a integridade e segurança dos dados, evitando modificações indevidas.

## 🔍 O que é **Encapsulamento**?

O encapsulamento é a prática de **esconder detalhes internos** de um objeto e fornecer uma interface segura para interação. Isso é feito definindo os atributos como **privados** e fornecendo métodos públicos para acessá-los e modificá-los (**getters** e **setters**).

### 📌 Benefícios do Encapsulamento:
- Protege os dados de acessos indevidos.
- Mantém a integridade do objeto.
- Facilita a manutenção e modificação do código.
- Permite controlar as regras de acesso e modificação dos atributos.

### 📖 Analogias para entender melhor

Imagine um **cofre** onde você guarda dinheiro. O dinheiro (dado) está protegido dentro do cofre (objeto), e você só pode acessá-lo usando a chave correta (métodos). Ninguém pode pegar o dinheiro diretamente sem seguir as regras do cofre.

Outro exemplo: pense em um **controle remoto**. Você pode aumentar ou diminuir o volume da TV pressionando botões (métodos), mas não pode modificar diretamente os circuitos internos da TV (dados protegidos).

Aqui está o texto formatado para o seu README:  

---

### 📌 Exemplo Técnico: Encapsulamento em um Sistema de Controle de Temperatura  

```java
// Classe ControladorDeTemperatura
class ControladorDeTemperatura {
    // Atributo privado (Encapsulamento)
    private double temperatura;

    // Construtor para definir uma temperatura inicial
    public ControladorDeTemperatura(double temperaturaInicial) {
        this.temperatura = temperaturaInicial;
    }

    // Método getter para obter a temperatura atual
    public double getTemperatura() {
        return temperatura;
    }

    // Método setter para definir a temperatura (com validação)
    public void setTemperatura(double novaTemperatura) {
        if (novaTemperatura >= -50 && novaTemperatura <= 100) {
            this.temperatura = novaTemperatura;
            System.out.println("Temperatura ajustada para: " + novaTemperatura + "°C");
        } else {
            System.out.println("Temperatura fora do limite permitido!");
        }
    }
}

// Classe principal para testar o encapsulamento
public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe ControladorDeTemperatura
        ControladorDeTemperatura sensor = new ControladorDeTemperatura(22.5);
        
        // Consultando a temperatura atual
        System.out.println("Temperatura atual: " + sensor.getTemperatura() + "°C");
        
        // Ajustando a temperatura para um valor válido
        sensor.setTemperatura(30.0);
        
        // Tentando definir uma temperatura inválida
        sensor.setTemperatura(150.0);
    }
}
```

## 🔍 Explicação do Código  

1. Criamos a classe `ControladorDeTemperatura` com um atributo **privado** `temperatura`, impedindo acesso direto a ele.  
2. Criamos um **construtor** para definir um valor inicial de temperatura.  
3. Criamos um **getter** (`getTemperatura()`) para permitir a consulta da temperatura.  
4. Criamos um **setter** (`setTemperatura()`) para alterar a temperatura **com uma validação** que impede valores fora do intervalo permitido (-50°C a 100°C).  
5. No `main`, criamos um objeto `sensor`, consultamos a temperatura, ajustamos para um valor válido e testamos um valor inválido.  

## 📌 Saída do Código  

```
Temperatura atual: 22.5°C  
Temperatura ajustada para: 30.0°C  
Temperatura fora do limite permitido!  
```

## 🔎 O que aprendemos?  

- **O atributo `temperatura` está encapsulado**, protegendo-o de alterações externas indevidas.  
- **O método `setTemperatura()` garante que só valores válidos sejam atribuídos**, evitando falhas no sistema.  
- **O encapsulamento melhora a segurança e controle dos dados**, garantindo que apenas operações seguras sejam realizadas.  

---
Aqui está o texto formatado para o seu README sobre **Herança** seguindo o mesmo padrão:

---

# 🏛️ Herança

Em **POO**, a **herança** é um princípio que permite que uma classe (subclasse) herde atributos e métodos de outra classe (superclasse). Isso promove **reutilização de código** e facilita a organização e manutenção do sistema.

## 🔍 O que é **Herança**?

A herança é um mecanismo que permite a criação de novas classes baseadas em classes existentes. A **classe filha** herda atributos e comportamentos da **classe pai**, podendo reutilizá-los, modificá-los ou adicionar novos.

### 📌 Benefícios da Herança:
- **Reutilização de código**: evita duplicação de código, tornando o sistema mais eficiente.
- **Facilita a manutenção**: mudanças na superclasse são refletidas nas subclasses.
- **Promove hierarquia e organização**: classes mais genéricas servem como base para classes mais específicas.
- **Permite polimorfismo**: possibilita que objetos da subclasse sejam tratados como objetos da superclasse.

### 📖 Analogias para entender melhor

Imagine um **carro elétrico**. Ele herda características de um **carro comum** (rodas, volante, portas), mas pode ter novas funcionalidades, como um motor elétrico.

Outro exemplo: pense em uma **árvore genealógica**. Uma pessoa herda características dos seus pais, mas também pode ter atributos únicos que a diferenciam.

---

### 📌 Exemplo Técnico: Herança em um Sistema de Pets  

```java
// Classe base (superclasse)
class Animal {
    protected String nome;
    protected int idade;

    public Animal(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    public void exibirDados() {
        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade + " anos");
    }
}

// Classe derivada (subclasse) que herda de Animal
class Cachorro extends Animal {
    private String raca;

    public Cachorro(String nome, int idade, String raca) {
        super(nome, idade); // Chama o construtor da superclasse
        this.raca = raca;
    }

    @Override
    public void exibirDados() {
        super.exibirDados(); // Reutiliza método da superclasse
        System.out.println("Raça: " + raca);
    }
}

// Classe principal para testar a herança
public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal("Bicho", 5);
        Cachorro cachorro = new Cachorro("Rex", 3, "Labrador");

        System.out.println("Dados do Animal:");
        animal.exibirDados();
        
        System.out.println("\nDados do Cachorro:");
        cachorro.exibirDados();
    }
}
```

## 🔍 Explicação do Código  

1. Criamos a **classe `Animal`** (superclasse), que contém atributos comuns como `nome` e `idade`.
2. Criamos a **classe `Cachorro`** (subclasse), que **herda** de `Animal` e adiciona um novo atributo `raca`.
3. No **construtor da subclasse**, usamos `super(nome, idade)` para chamar o construtor da superclasse.
4. Sobrescrevemos (`@Override`) o método `exibirDados()` na subclasse para incluir a raça do cachorro.
5. No `main`, criamos um objeto da superclasse (`Animal`) e um da subclasse (`Cachorro`) e chamamos `exibirDados()` para ambos.

## 👉 Saída do Código  

```
Dados do Animal:
Nome: Bicho
Idade: 5 anos

Dados do Cachorro:
Nome: Rex
Idade: 3 anos
Raça: Labrador
```

## 🔎 O que aprendemos?  

- **A classe `Cachorro` herda os atributos e métodos de `Animal`**, reutilizando código.  
- **A palavra-chave `super` permite acessar métodos da superclasse** dentro da subclasse.  
- **Podemos sobrescrever métodos (`@Override`) para personalizar o comportamento da subclasse**.  
- **Herança permite criar hierarquias organizadas e reutilizar código eficientemente**. 🚀



---
### 4️⃣ Abstração

A **abstração** permite definir **o que um objeto faz**, sem expor **como ele faz**.

📌 **Exemplo:** Criamos uma classe abstrata `Animal` com o método abstrato `emitirSom()`, que será implementado nas subclasses `Cachorro` e `Gato`.

```java
abstract class Animal {
    abstract void emitirSom();
}

class Cachorro extends Animal {
    @Override
    void emitirSom() {
        System.out.println("O cachorro late: Au Au!");
    }
}

class Gato extends Animal {
    @Override
    void emitirSom() {
        System.out.println("O gato mia: Miau!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal meuCachorro = new Cachorro();
        meuCachorro.emitirSom();

        Animal meuGato = new Gato();
        meuGato.emitirSom();
    }
}
```

🔍 **Explicação:**
- `Animal` é abstrata e define `emitirSom()`, sem implementação.
- `Cachorro` e `Gato` implementam `emitirSom()` de maneira específica.
- Criamos objetos que usam polimorfismo para chamar `emitirSom()`.

