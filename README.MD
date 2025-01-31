# Programação Orientada a Objetos (POO) 🚀

Este repositório é dedicado ao meu aprendizado sobre **Programação Orientada a Objetos (POO)**. Aqui, explico de forma simples e intuitiva os principais conceitos da POO com exemplos práticos em **Java**, utilizando apenas **animais de estimação** como exemplo para facilitar o entendimento.

## 📌 Conceitos Abordados

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
### 2️⃣ Encapsulamento

O **encapsulamento** protege os dados internos de um objeto, restringindo o acesso direto e permitindo modificá-los apenas por meio de métodos específicos.

📌 **Exemplo:** Imagine um **gato** cujo nome e idade só podem ser acessados ou alterados por meio de métodos.

```java
class Gato {
    private String nome;
    private int idade;

    // Construtor
    public Gato(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    // Métodos getters e setters
    public String getNome() {
        return nome;
    }
    
    public void setNome(String nome) {
        this.nome = nome;
    }
    
    public int getIdade() {
        return idade;
    }
    
    public void setIdade(int idade) {
        if (idade > 0) {
            this.idade = idade;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Gato meuGato = new Gato("Mia", 2);
        System.out.println("Nome: " + meuGato.getNome());
        System.out.println("Idade: " + meuGato.getIdade());
    }
}
```

🔍 **Explicação:**
- `nome` e `idade` são privados (`private`), protegendo o acesso direto.
- Criamos métodos `get` e `set` para manipular os atributos de forma controlada.
- O construtor inicializa os valores ao criar um objeto da classe `Gato`.

---
### 3️⃣ Herança

A **herança** permite que uma classe reutilize atributos e métodos de outra classe, evitando repetição de código.

📌 **Exemplo:** Criamos uma **superclasse "Animal"** e as subclasses **"Cachorro"** e **"Gato"** que herdam dela.

```java
class Animal {
    String nome;
    int idade;
    
    void emitirSom() {
        System.out.println("O animal faz um som.");
    }
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
        Cachorro dog = new Cachorro();
        dog.nome = "Rex";
        dog.idade = 4;
        dog.emitirSom();
        
        Gato cat = new Gato();
        cat.nome = "Mia";
        cat.idade = 2;
        cat.emitirSom();
    }
}
```

🔍 **Explicação:**
- `Cachorro` e `Gato` herdam atributos e métodos da classe `Animal`.
- Sobrescrevemos o método `emitirSom()` em cada subclasse para personalizar o comportamento.
- Criamos objetos `dog` e `cat` e chamamos seus métodos.

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

---
## 📢 Conclusão

A Programação Orientada a Objetos é uma abordagem poderosa para o desenvolvimento de software. Com esses conceitos, podemos escrever **código mais organizado, reutilizável e fácil de manter**.

Se você gostou, ⭐ este repositório no **GitHub**!

