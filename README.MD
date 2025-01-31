# Programação Orientada a Objetos (POO) 🚀

Este repositório é dedicado ao meu aprendizado sobre **Programação Orientada a Objetos (POO)**. Aqui, explico de forma simples e intuitiva os principais conceitos da POO com exemplos práticos em **Java**, utilizando apenas **animais de estimação** como exemplo para facilitar o entendimento.

## 📌 Conceitos Abordados

Classes e Objetos

Em **POO** classes são modelos que definem as características e comportamentos de um objeto. Já os objetos são instâncias dessas classes, ou seja, representam entidades específicas baseadas no modelo da classe.

Uma classe é uma estrutura que agrupa atributos (dados) e métodos (comportamentos) relacionados a um conceito.
Um objeto é uma instância de uma classe, ou seja, uma ocorrência específica que possui os atributos e comportamentos definidos na classe.

Pense em uma classe como uma receita de bolo. A receita contém todas as instruções e ingredientes necessários para fazer um bolo, mas ela por si só não é um bolo real.
Agora, quando você segue a receita e assa um bolo, você cria um objeto, que é um bolo real baseado nessa receita.

Outro exemplo: Imagine que temos uma classe **"Animal"**. Essa classe define que todo animal tem um nome e uma idade. Mas um animal específico, como um cachorro chamado **"Rex"**, seria um objeto dessa classe.

Se tivermos um segundo cachorro chamado **"Bolt"**, ele também seria um objeto da classe "Animal", com seu próprio nome e idade, mas ainda seguindo o mesmo modelo da classe.

Resumindo a ideia principal de classes e objetos: a classe define o modelo e os objetos são as instâncias concretas desse modelo.

📌 Exemplo Técnico:

// Definição da classe Animal
class Animal {
    String nome;
    int idade;

    // Método para exibir informações do animal
    void exibirInformacoes() {
        System.out.println("Nome: " + nome + ", Idade: " + idade + " anos");
    }
}

// Classe principal
public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Animal
        Animal pet = new Animal(); // Aqui criamos um objeto chamado "pet"
        pet.nome = "Rex"; // Definimos o nome do pet
        pet.idade = 3; // Definimos a idade do pet
        
        // Chamando o método para exibir as informações do animal
        pet.exibirInformacoes();
    }
}

🔍 Explicação do Código:

Criamos a classe Animal com atributos nome e idade.

Criamos um método exibirInformacoes() que imprime os detalhes do animal.

No método main, instanciamos um objeto pet da classe Animal, definimos seus atributos e chamamos o método para exibir suas informações.

O objeto dessa classe é um pet chamado "Rex" com 3 anos de idade.

📌 Saída do Código:

Nome: Rex, Idade: 3 anos


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

