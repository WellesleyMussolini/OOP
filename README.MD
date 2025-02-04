# Programação Orientada a Objetos (POO)

Este repositório reúne conceitos fundamentais da **Programação Orientada a Objetos (POO)**, apresentados de forma simples e intuitiva com exemplos práticos em **Java**. Para facilitar o entendimento.

## Sumário

1. [Classes e Objetos](#classes-e-objetos)
2. [Encapsulamento](#encapsulamento)
3. [Herança](#herança)
4. [Abstração](#abstração)
5. [Polimorfismo](#polimorfismo)
6. [Interfaces](#interfaces)
7. [Conclusão](#conclusão)

---

## 1. Classes e Objetos

Em **POO**, **classes** são modelos que definem as características (**estado**) e os comportamentos (**métodos**) de um objeto. Um **objeto** é uma instância de uma classe, ou seja, uma ocorrência específica que possui os atributos e comportamentos definidos na classe.

### Conceitos Básicos

- **Estado**: Conjunto de atributos (dados) que descrevem o objeto em um determinado momento.
- **Métodos**: Conjunto de ações (funções) que o objeto pode executar para interagir ou alterar seu estado.

### Analogias

- **Receita de Bolo**: A classe é a receita, que contém os ingredientes (atributos) e o modo de preparo (métodos). O bolo assado é o objeto, ou seja, uma instância real da receita.
- **Animal**: Imagine uma classe `Animal` que define que todo animal tem um nome e uma idade. Um cachorro chamado "Rex" é um objeto dessa classe, possuindo seus próprios valores para os atributos.

### Exemplo Prático

```java
// Definição da classe Animal
class Animal {
    String nome; // Estado: nome do animal
    int idade;   // Estado: idade do animal

    // Método: exibe informações do animal
    void exibirInformacoes() {
        System.out.println("Nome: " + nome + ", Idade: " + idade + " anos");
    }
}

// Classe principal para testar a classe Animal
public class Main {
    public static void main(String[] args) {
        Animal pet = new Animal(); // Criação do objeto (instância da classe Animal)
        pet.nome = "Rex";          // Definindo o estado do objeto
        pet.idade = 3;
        
        pet.exibirInformacoes();   // Executando um método (comportamento)
    }
}
```

**Saída do Código:**
```
Nome: Rex, Idade: 3 anos
```

---

## 2. Encapsulamento

O **encapsulamento** é o princípio que protege os dados internos de um objeto, restringindo o acesso direto aos seus atributos e permitindo manipulações somente por meio de métodos controlados (getters e setters). Isso mantém a integridade e a segurança dos dados.

### Benefícios

- Protege os dados de acessos indevidos.
- Facilita a manutenção e a modificação do código.
- Permite controlar as regras de acesso e modificação dos atributos.

### Analogia

Imagine um **cofre**: o dinheiro está protegido e só pode ser acessado com a chave certa (métodos), evitando que qualquer um acesse diretamente o conteúdo.

### Exemplo Prático

```java
// Classe que exemplifica o encapsulamento
class ControladorDeTemperatura {
    // Atributo privado, não acessível diretamente
    private double temperatura;

    // Construtor que define uma temperatura inicial
    public ControladorDeTemperatura(double temperaturaInicial) {
        this.temperatura = temperaturaInicial;
    }

    // Getter para consultar a temperatura
    public double getTemperatura() {
        return temperatura;
    }

    // Setter para alterar a temperatura, com validação
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
        ControladorDeTemperatura sensor = new ControladorDeTemperatura(22.5);
        System.out.println("Temperatura atual: " + sensor.getTemperatura() + "°C");
        sensor.setTemperatura(30.0);  // Valor válido
        sensor.setTemperatura(150.0); // Valor inválido
    }
}
```

**Saída do Código:**
```
Temperatura atual: 22.5°C  
Temperatura ajustada para: 30.0°C  
Temperatura fora do limite permitido!
```

---

## 3. Herança

A **herança** permite que uma classe (subclasse) herde atributos e métodos de outra classe (superclasse), promovendo a reutilização de código e a organização hierárquica.

### Benefícios

- Evita duplicação de código.
- Facilita a manutenção, pois alterações na superclasse são refletidas nas subclasses.
- Permite a criação de hierarquias organizadas.

### Exemplo Prático

```java
// Superclasse Animal
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

// Subclasse Cachorro que herda de Animal
class Cachorro extends Animal {
    private String raca;

    public Cachorro(String nome, int idade, String raca) {
        super(nome, idade); // Invoca o construtor da superclasse
        this.raca = raca;
    }

    @Override
    public void exibirDados() {
        super.exibirDados(); // Reaproveita o método da superclasse
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

**Saída do Código:**
```
Dados do Animal:
Nome: Bicho
Idade: 5 anos

Dados do Cachorro:
Nome: Rex
Idade: 3 anos
Raça: Labrador
```

---

## 4. Abstração

A **abstração** consiste em ocultar detalhes de implementação e fornecer somente as funcionalidades essenciais. Isso permite definir classes e métodos que servem de modelo, sem precisar especificar todos os detalhes.

### Benefícios

- Reduz a complexidade do código.
- Separa a lógica de implementação dos detalhes internos.
- Facilita a manutenção e a expansão do sistema.

### Exemplo Prático

```java
// Classe abstrata que serve como modelo para pets
abstract class Pet {
    protected String nome;
    protected int idade;

    public Pet(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    // Método abstrato: não possui implementação na classe Pet
    public abstract void fazerSom();

    // Método concreto: implementado na classe abstrata e herdado pelas subclasses
    public void exibirInfo() {
        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade + " anos");
    }
}

// Subclasse Cachorro que implementa o método abstrato
class Cachorro extends Pet {
    public Cachorro(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void fazerSom() {
        System.out.println(nome + " diz: Au Au! 🐶");
    }
}

// Subclasse Gato que implementa o método abstrato
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
        Pet cachorro = new Cachorro("Rex", 5);
        Pet gato = new Gato("Mia", 3);

        cachorro.exibirInfo();
        cachorro.fazerSom();

        System.out.println();

        gato.exibirInfo();
        gato.fazerSom();
    }
}
```

**Saída do Código:**
```
Nome: Rex  
Idade: 5 anos  
Rex diz: Au Au! 🐶  

Nome: Mia  
Idade: 3 anos  
Mia diz: Miau! 🐱
```

---

## 5. Polimorfismo

O **polimorfismo** permite que métodos com o mesmo nome tenham comportamentos diferentes, dependendo do objeto que os invoca. Essa característica torna o código mais flexível e extensível.

### Tipos de Polimorfismo

1. **Sobrescrita (Override):** Uma subclasse redefine o comportamento de um método herdado da superclasse.  
2. **Sobrecarga (Overload):** Métodos com o mesmo nome, mas com diferentes parâmetros, dentro de uma mesma classe.

### Exemplo Prático (Sobrescrita)

```java
// Superclasse Animal
class Animal {
    public void fazerSom() {
        System.out.println("O animal faz um som.");
    }
}

// Subclasse Cachorro sobrescrevendo o método
class Cachorro extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("O cachorro late: Au Au!");
    }
}

// Subclasse Gato sobrescrevendo o método
class Gato extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("O gato mia: Miau!");
    }
}

// Classe principal para testar o polimorfismo
public class Main {
    public static void main(String[] args) {
        Animal meuAnimal1 = new Cachorro();
        Animal meuAnimal2 = new Gato();

        meuAnimal1.fazerSom(); // Saída: O cachorro late: Au Au!
        meuAnimal2.fazerSom(); // Saída: O gato mia: Miau!
    }
}
```

**Saída do Código:**
```
O cachorro late: Au Au!
O gato mia: Miau!
```

---

## 6. Interfaces

**Interfaces** são contratos que definem quais métodos uma classe deve implementar, sem fornecer uma implementação concreta. Elas garantem que diferentes classes sigam um padrão comum.

### Benefícios

- Padronizam a comunicação entre classes.
- Permitem que classes não relacionadas implementem os mesmos métodos, facilitando a interoperabilidade.
- Promovem a flexibilidade e a reutilização do código.

### Exemplo Prático

```java
// Definição da interface Animal
interface Animal {
    void fazerSom(); // Método sem implementação
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

// Classe principal para testar a interface
public class Main {
    public static void main(String[] args) {
        Animal meuAnimal1 = new Cachorro();
        Animal meuAnimal2 = new Gato();

        meuAnimal1.fazerSom(); // Saída: O cachorro late: Au Au!
        meuAnimal2.fazerSom(); // Saída: O gato mia: Miau!
    }
}
```

**Saída do Código:**
```
O cachorro late: Au Au!
O gato mia: Miau!
```

---

## 7. Resumo

- **Classes e Objetos:** Definem os modelos (classes) e suas instâncias (objetos) com estados e comportamentos.  
- **Encapsulamento:** Protege os dados internos, permitindo o acesso seguro por meio de métodos.  
- **Herança:** Permite a criação de hierarquias e a reutilização de código entre classes relacionadas.  
- **Abstração:** Oculta os detalhes de implementação, focando nas funcionalidades essenciais.  
- **Polimorfismo:** Permite métodos com o mesmo nome se comportarem de maneira diferente, conforme o objeto que os invoca.  
- **Interfaces:** Estabelecem contratos que garantem a implementação de métodos padronizados, promovendo flexibilidade.

