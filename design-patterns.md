# Minhas anotações | Design Patterns

## Creational Patterns
> “In software engineering, creational design patterns are design patterns that deal with object creation mechanisms, trying to create objects in a manner suitable to the situation. The basic form of object creation could result in design problems or added complexity to the design. Creational design patterns solve this problem by somehow controlling this object creation”.

### Builder
> Bem similar a Factory e Multition, com a diferença de que, nesse padrão, ele não somente cria objetos, mas os prepara para o restante da aplicação. Ou seja, esse padrão, define os passos para a criação de um objeto.

### Factory
Benefícios:
* Se precisar mudar, renomear ou substituir a classe Automobile futuramente você pode fazer e só terá que modificar o código na “Factory”, em vez de em todos os lugares do seu projeto onde você usa a classe Automobile.
* Caso a criação do objeto seja um processo complicado, você pode executar todo esse trabalho na factory, em vez de repetí-lo toda vez que precisar criar uma nova instância da classe.
Usar o padrão de “Factory” não é sempre necessário. As vezes, a “Factory” acaba adicionando complexidade indesejada. Entretanto se você estiver realizando um projeto um pouco maior ou mais complexo você pode se salvar de muitos problemas com o uso do padrão “Factory”.

## Structural Patterns
> “In Software Engineering, Structural Design Patterns are Design Patterns that ease the design by identifying a simple way to realize relationships between entities”.

### Bridge
> Padrão extremamente utilizado para criação de temas. Imagine um site com uma quantidade de páginas onde o tema (ex: dark, green, blue) pode ser escolhido. Outro exemplo, seria uma N dispositivos utilizando N serviços de mensagem.
A ideia desse padrão seria em fazer uma ponte entre classes do tipo N->N.

### Composite
Em breve...

### Decorator
> Adiciona novas funcionalidades a classes instanciadas dinamicamente.
Imagina a seguinte situação: Existem 3 preços praticados para venda de pipoca. A pipoca simples, pipoca com refrigerante e pipoca com chocolate. Se você precisar que uma classe seja “complemento” direto de outra no momento da instância do primeiro objeto, esse padrão se encaixa muito bem. Importante ressaltar que o acoplamento entre classes é alta.
### Injeção de dependência
Em breve..

### Facade
> É usado quando um sistema é muito complexo ou difícil de entender, já que possui um grande número de classes independentes ou se trechos de código fonte estão indisponíveis. Este padrão esconde as complexidades de um sistema maior e provê uma interface simplificada

Um bom exemplo, seria um jogo. Na classe principal teria o método atirar e correr. Na classe facade, um function p/ o botão B, por exemplo, onde ele correria e atiraria ao mesmo tempo.

Imagine uma implementação onde envolve grupos de comportamentos.
A classe principal contém todos os comportamentos. A classe facade contém os grupos. Exemplo:

```php
    class Principal
    {
        function A(){}
        function B(){}
        function C(){}
        function D(){}
        function E(){}
        function F(){}
    }

    class Facade
    {
        private $principal;
        function __construct(Principal $principal){
            $this->principal = $principal;
        }

        function executaGrupo1(){
            $this->principal->A();
            $this->principal->B();
            $this->principal->C();
        }

        function executaGrupo2(){
            $this->principal->D();
            $this->principal->E();
            $this->principal->F();
        }
    }

```

### Fluent Interface
> Os métodos são nomeados com o intuito de deixar a chamada mais intuitiva.
Muito utilizado para a criação de APIs onde há métodos encadeados. Outro exemplo de uso, seria uma QueryBuilder de SQL onde os atributos são encadeados. Exemplo: →where()→limit() Outro exemplo: QueryBuilder para classe de disparo de e-mail: new Email()->from()->to()->subject()..

### Flywight
Em breve

### Proxy
Em breve...

### Registry
Em breve...

## Behavioral Patterns
> “In software engineering, behavioral, design patterns that identify common communication patterns between objects and realize these patterns. By doing so, these patterns increase flexibility in carrying out this communication”.

### Chain of responsability
> Função de evitar a dependência entre um objeto receptor e um objeto solicitante. Consiste em uma série de objetos receptores e de objetos de solicitação, onde cada objetos de solicitação possui uma lógica interna que separa quais são tipos de objetos receptores que podem ser manipulados. O restante é passado para o próximo objetos de solicitação da cadeia.
Devido à isso, é um padrão que utiliza a ideia de baixo acoplamento por permitir que outros objetos da cadeia tenham a oportunidade de tratar uma solicitação.
Cai como uma luva quando temos uma lista de comandos a serem executados de acordo com algum cenário em específico, e sabemos também qual o próximo cenário que deve ser validado, caso o anterior não satisfaça a condição.
Nesses casos, o Chain of Responsibility nos possibilita a separação de responsabilidades em classes pequenas e enxutas, e ainda provê uma maneira flexível e desacoplada de juntar esses comportamentos novamente.

### Command
Em breve...

### Interpreter
> O padrão Interpreter é geralmente útil para interpretar DSLs.

### Interator
Em breve...

### Mediator
Em breve...

### Memento
> Imagine, no Mind Meister por exemplo, eu colocar um nome na caixa, modificar esse nome e agora eu clico na seta da skol à esquerda para retomar a ultima ação que eu realizei. Isso é o memento. Ele grava o estado do objeto numa classe como uma espécie de “repositório” onde eu posso pegar o estado quando quiser (durante o tempo de execução daquele objeto).

### Observer
> Sempre que uma classe precisa saber que uma ação ocorreu ou um estado foi alterado em outra classe (ou nela mesmo).
Basicamente você tem dois agentes, a classe observável (conhecida como Subject) e a observadora.
Na classe observável você precisa ter um estado: a lista que guarda os assinantes; e três comportamentos: quem faz a adição de um novo assinante na lista, quem faz a retirada de um assinante, e quem notifica a lista de assinantes que algum evento relevante para eles ocorreu.
Na classe observadora você precisa de uma ação a ser realizada quando for notificado que algo que lhe interessa ocorreu.
Exemplos de implementação:
  * Um arquivo foi modificado no sistema de arquivos
  * Uma propriedade preço foi modificada em uma classe produto
  * Um click foi dado em botão
  * Recebeu uma informação da rede
  * Um objeto visual do jogo se encontrou com outro objeto (acertou o alvo)
  * Uma atualização no banco de dados ocorreu

### Proxy
Em breve...

### Specification
Em breve...

### State
Em breve...

### Strategy
> Encapsula famílias específicas de algoritimos permitindo com que a classe cliente responsável por instanciar esse algoritimo em particular não necessite de conhecimento sobre sua implementação atual.
Através do encapsulamento do algoritimo, faz com que seu código de forma limpa e clara para que outros desenvolvedores possam facilmente adicionar novos tipos de saída sem que isso afete o código cliente.

### Template Method
Em breve...

### Visitor
Em breve...

## References
* [PHP Right Way](http://br.phptherightway.com/pages/Design-Patterns.html)
* [Design Patterns PHP](http://designpatternsphp.readthedocs.io/pt_BR/latest/README.html)
* [Ocramius](https://ocramius.github.io/blog/fluent-interfaces-are-evil/) - Fluent Influence
* [Wiki](https://pt.wikipedia.org/wiki/Chain_of_Responsibility) - Chain of Responsability
* [PHP Lab](http://www.phplab.info/categories/design-pattern/template-method-pattern) - Template Method
* [PHP Lab](http://www.phplab.info/categories/design-pattern/adapter-pattern) - Adapter
* [Devmedia](https://www.devmedia.com.br/design-patterns-aplicando-os-padroes-builder-singleton-e-prototype/31023) - Builder & Singleton
* [kamranahmedse](https://github.com/kamranahmedse/design-patterns-for-humans) - Best examples | For dummies
* [Stackoverflow](https://pt.stackoverflow.com/questions/106955/o-que-%c3%a9-fluent-interface) - Fluent interfaces
* [Injeção de dependência](http://fabien.potencier.org/what-is-dependency-injection.html) -
* [Composite](https://stackoverflow.com/questions/30136414/composite-pattern-and-dependency-injection) -



