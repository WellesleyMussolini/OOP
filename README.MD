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

## 📌 Exemplo Técnico:

```java
// Definição da classe ContaBancaria
class ContaBancaria {
    // Atributos privados (Encapsulamento)
    private String titular;
    private double saldo;

    // Construtor para inicializar os valores
    public ContaBancaria(String titular, double saldoInicial) {
        this.titular = titular;
        this.saldo = saldoInicial;
    }

    // Método getter para obter o saldo
    public double getSaldo() {
        return saldo;
    }

    // Método para depositar dinheiro (modifica saldo com regras)
    public void depositar(double valor) {
        if (valor > 0) {
            saldo += valor;
            System.out.println("Depósito de R$" + valor + " realizado com sucesso.");
        } else {
            System.out.println("Valor de depósito inválido!");
        }
    }

    // Método para sacar dinheiro (modifica saldo com validação)
    public void sacar(double valor) {
        if (valor > 0 && valor <= saldo) {
            saldo -= valor;
            System.out.println("Saque de R$" + valor + " realizado com sucesso.");
        } else {
            System.out.println("Saldo insuficiente ou valor inválido!");
        }
    }
}

// Classe principal para testar o encapsulamento
public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe ContaBancaria
        ContaBancaria minhaConta = new ContaBancaria("João", 1000.00);
        
        // Consultando o saldo via método getter
        System.out.println("Saldo atual: R$" + minhaConta.getSaldo());
        
        // Tentando depositar um valor
        minhaConta.depositar(500.00);
        System.out.println("Saldo atual: R$" + minhaConta.getSaldo());
        
        // Tentando sacar um valor
        minhaConta.sacar(300.00);
        System.out.println("Saldo atual: R$" + minhaConta.getSaldo());
        
        // Tentativa de saque maior que o saldo
        minhaConta.sacar(2000.00);
    }
}
```

### 🔍 Explicação do Código:
1. Criamos a classe `ContaBancaria` com os atributos `titular` e `saldo` **privados**, garantindo que só possam ser acessados por métodos específicos.
2. Implementamos um **construtor** para inicializar a conta com um saldo inicial.
3. Criamos um **getter** (`getSaldo()`) para permitir a consulta do saldo.
4. Criamos um método `depositar(double valor)`, que adiciona dinheiro ao saldo, mas apenas se o valor for positivo.
5. Criamos um método `sacar(double valor)`, que permite retirar dinheiro da conta **apenas se houver saldo suficiente**.
6. No `main`, instanciamos um objeto `minhaConta`, realizamos depósitos, saques e tentamos fazer um saque maior que o saldo disponível para ver como o encapsulamento protege os dados.

### 📌 Saída do Código:

```
Saldo atual: R$1000.0
Depósito de R$500.0 realizado com sucesso.
Saldo atual: R$1500.0
Saque de R$300.0 realizado com sucesso.
Saldo atual: R$1200.0
Saldo insuficiente ou valor inválido!
```

### 🔎 O que aprendemos?
- **Os atributos estão protegidos** e não podem ser modificados diretamente.
- **Os métodos controlam o acesso aos dados**, garantindo que apenas operações válidas sejam realizadas.
- **O encapsulamento protege a integridade do objeto**, impedindo mudanças indesejadas nos atributos.

Dessa forma, **o encapsulamento melhora a segurança e organização do código, facilitando a manutenção e prevenção de erros.** 🚀



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

