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


# Abstração  

A **Abstração** é um dos pilares da **Programação Orientada a Objetos (POO)** e consiste em **ocultar detalhes de implementação** e **fornecer apenas funcionalidades essenciais**.  

Ela permite que os objetos sejam representados de forma mais genérica, focando no que é relevante para a aplicação e deixando os detalhes internos escondidos.  

## 🔍 O que é **Abstração**?  

A abstração permite definir **classes genéricas** que representam um conceito, sem se preocupar com os detalhes específicos de cada implementação.  

Isso é feito por meio de **classes abstratas** e **métodos abstratos**, que servem como um modelo para outras classes.  

### 📌 Benefícios da Abstração:  

- Reduz a complexidade do código.  
- Facilita a reutilização e manutenção.  
- Separa a lógica de implementação dos detalhes internos.  
- Permite criar sistemas mais flexíveis e organizados.  

### 📖 Analogias para entender melhor  

Imagine uma **rede social para pets**. Você pode visualizar um perfil, curtir fotos e ver informações básicas, mas **não sabe** como os dados são armazenados ou processados internamente.  

Outro exemplo: pense em um **controle de videogame**. Você aperta um botão para pular, mas não precisa saber como os circuitos internos processam esse comando.  

---

# 📌 Exemplo Técnico: Abstração em um Sistema de Pets  

```java
// Classe abstrata Pet
abstract class Pet {
    protected String nome;
    protected int idade;

    public Pet(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    // Método abstrato (deve ser implementado pelas subclasses)
    public abstract void fazerSom();

    // Método concreto (compartilhado por todas as subclasses)
    public void exibirInfo() {
        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade + " anos");
    }
}

// Classe Cachorro herda de Pet e implementa o método abstrato
class Cachorro extends Pet {
    public Cachorro(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void fazerSom() {
        System.out.println(nome + " diz: Au Au! 🐶");
    }
}

// Classe Gato herda de Pet e implementa o método abstrato
class Gato extends Pet {
    public Gato(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void fazerSom() {
        System.out.println(nome + " diz: Miau! 🐱");
    }
}

// Classe principal para testar a abstração
public class Main {
    public static void main(String[] args) {
        // Criando objetos das subclasses
        Pet cachorro = new Cachorro("Rex", 5);
        Pet gato = new Gato("Mia", 3);

        // Exibindo informações e sons dos pets
        cachorro.exibirInfo();
        cachorro.fazerSom();

        System.out.println();

        gato.exibirInfo();
        gato.fazerSom();
    }
}
```

---

## 🔍 Explicação do Código  

1. Criamos uma **classe abstrata `Pet`**, que serve como um modelo para todos os pets.  
2. Definimos um **método abstrato `fazerSom()`**, que **não tem implementação na classe `Pet`** e deve ser implementado nas subclasses.  
3. Criamos as classes `Cachorro` e `Gato`, que **herdam de `Pet` e implementam `fazerSom()` com sons diferentes**.  
4. No `main`, criamos objetos de `Cachorro` e `Gato`, chamamos `exibirInfo()` e `fazerSom()` para demonstrar a abstração.  

---

## 📌 Saída do Código  

```
Nome: Rex  
Idade: 5 anos  
Rex diz: Au Au! 🐶  

Nome: Mia  
Idade: 3 anos  
Mia diz: Miau! 🐱  
```

---

## 🔎 O que aprendemos?  

- **A classe `Pet` é abstrata**, pois representa um conceito genérico.  
- **O método `fazerSom()` é abstrato**, forçando cada pet a ter seu próprio som.  
- **A abstração permite definir uma estrutura comum** sem precisar detalhar a implementação na superclasse.  
- **Isso torna o código mais organizado, reutilizável e fácil de expandir** (podemos adicionar novos pets sem modificar o código existente). 🚀  

---

# 🏆 Polimorfismo  

O **Polimorfismo** é um dos pilares da **Programação Orientada a Objetos (POO)** e permite que um mesmo método tenha **diferentes comportamentos** dependendo do objeto que o invoca.  

Isso torna o código mais flexível, reutilizável e fácil de manter.  

## 🔍 O que é **Polimorfismo**?  

Polimorfismo significa **"muitas formas"**. Ele permite que um mesmo método seja utilizado por diferentes classes, podendo ser de duas formas:  

1. **Polimorfismo de Sobrescrita (Override)** – Quando uma **subclasse modifica** o comportamento de um método herdado da superclasse.  
2. **Polimorfismo de Sobrecarga (Overload)** – Quando há **métodos com o mesmo nome**, mas com parâmetros diferentes dentro da mesma classe.  

---

## 📌 Exemplo Técnico: Polimorfismo com Animais  

```java
// Classe base (superclasse)
class Animal {
    public void fazerSom() {
        System.out.println("O animal faz um som.");
    }
}

// Classe derivada (subclasse) - Polimorfismo por Sobrescrita
class Cachorro extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("O cachorro late: Au Au!");
    }
}

// Outra subclasse - Polimorfismo por Sobrescrita
class Gato extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("O gato mia: Miau!");
    }
}

// Classe principal
public class Main {
    public static void main(String[] args) {
        Animal meuAnimal1 = new Cachorro();
        Animal meuAnimal2 = new Gato();

        meuAnimal1.fazerSom(); // Saída: O cachorro late: Au Au!
        meuAnimal2.fazerSom(); // Saída: O gato mia: Miau!
    }
}
```

## 📌 Saída do Código  

```
O cachorro late: Au Au!  
O gato mia: Miau!  
```

### ✅ O que aprendemos?  

✔ **A classe `Animal` define um método genérico `fazerSom()`.**  
✔ **As subclasses `Cachorro` e `Gato` sobrescrevem esse método com seu próprio comportamento.**  
✔ **Isso permite que possamos chamar `fazerSom()` em qualquer `Animal`, sem precisar saber qual tipo específico ele é.**  

---

# 🎭 Interfaces  

As **interfaces** são contratos que definem **quais métodos** uma classe deve implementar, sem fornecer uma implementação concreta.  

Isso ajuda a garantir que diferentes classes sigam um **padrão comum**, promovendo reutilização e flexibilidade no código.  

## 🔍 O que é uma **Interface**?  

Uma interface contém **apenas a assinatura dos métodos**, sem definir como eles devem ser implementados.  

As classes que **"assinam o contrato"** (implementam a interface) **devem fornecer suas próprias implementações**.  

---

## 📌 Exemplo Técnico: Interface para Animais  

```java
// Definição da interface
interface Animal {
    void fazerSom(); // Método sem implementação (obrigatório nas classes que implementam)
}

// Classe Cachorro implementa a interface Animal
class Cachorro implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("O cachorro late: Au Au!");
    }
}

// Classe Gato implementa a interface Animal
class Gato implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("O gato mia: Miau!");
    }
}

// Classe principal
public class Main {
    public static void main(String[] args) {
        Animal meuAnimal1 = new Cachorro();
        Animal meuAnimal2 = new Gato();

        meuAnimal1.fazerSom(); // Saída: O cachorro late: Au Au!
        meuAnimal2.fazerSom(); // Saída: O gato mia: Miau!
    }
}
```

## 📌 Saída do Código  

```
O cachorro late: Au Au!  
O gato mia: Miau!  
```

### ✅ O que aprendemos?  

✔ **A interface `Animal` define um contrato com o método `fazerSom()`.**  
✔ **As classes `Cachorro` e `Gato` são obrigadas a implementar esse método.**  
✔ **Podemos usar `Animal` como um tipo genérico, permitindo um código mais flexível.**  

---

## 🚀 Conclusão  

- **Polimorfismo** permite que um método tenha **diferentes comportamentos** dependendo da classe.  
- **Interfaces** ajudam a padronizar métodos sem definir a implementação, garantindo que diferentes classes sigam um contrato comum.  
- Ambos melhoram a **organização, flexibilidade e reutilização do código**! 🎯  

