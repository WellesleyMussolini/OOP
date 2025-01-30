# Programação Orientada a Objetos (POO) 🚀

Este repositório é dedicado ao meu aprendizado sobre **Programação Orientada a Objetos (POO)**. Aqui, explico de forma simples e intuitiva os principais conceitos da POO com exemplos práticos em **Java**, utilizando apenas **animais de estimação** como exemplo para facilitar o entendimento.

## 📌 Conceitos Abordados

### Classes e Objetos

Na POO, **classes** são modelos que definem as características e comportamentos de um objeto. Já os **objetos** são instâncias dessas classes, ou seja, representam entidades específicas baseadas no modelo da classe.

📌 **Exemplo:** Pense em uma **classe "Animal"**. Todos os animais de estimação compartilham características comuns (nome, idade, som) e comportamentos (emitir som). Cada cachorro ou gato específico é um **objeto** dessa classe.

```java
// Definição da classe Animal
class Animal {
    String nome;
    int idade;

    // Método para exibir informações do animal
    void exibirInfo() {
        System.out.println("Nome: " + nome + ", Idade: " + idade + " anos");
    }
}

// Classe principal
public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Animal
        Animal pet = new Animal();
        pet.nome = "Rex";
        pet.idade = 3;
        
        // Chamando método do objeto
        pet.exibirInfo();
    }
}
```

🔍 **Explicação:**
- Criamos a classe `Animal` com atributos `nome` e `idade`.
- Criamos um método `exibirInfo()` para exibir os dados do animal.
- No `main`, instanciamos um objeto `pet` da classe `Animal`, definimos seus atributos e chamamos o método para exibir suas informações.

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

