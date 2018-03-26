# Minhas anotações | Design Patterns

## Definição
> Design Patters é uma forma prevista, estruturada e documentada de solucionar um dado problema que é bastante comum

## Creational Patterns
> Abstraem e escondem o processo de instanciação. O sistema torna-se independente da maneira como o objeto é composto, construido e representado”.

### Builder
Separa a construção de um objeto da sua representação, de modo que o mesmo processo de construção possa criar diferentes representações.
Similar a Factory e Multition, com a diferença de que, nesse padrão, ele não apenas cria objetos, mas os prepara para o restante da aplicação. Ou seja, Builder define os passos para a criação de um objeto.

### Factory
Define uma interface para criar um objeto, mas deixa as subclasses decidirem qual classe a ser instanciada. O Factory Method permite a uma classe postergar a instanciação às subclasses.

* Se precisar mudar, renomear ou substituir a classe Automobile futuramente você pode fazer e só terá que modificar o código na “Factory”, em vez de em todos os lugares do seu projeto onde você usa a classe Automobile.
* Caso a criação do objeto seja um processo complicado, você pode executar todo esse trabalho na factory, em vez de repetí-lo toda vez que precisar criar uma nova instância da classe.
Usar o padrão de “Factory” não é sempre necessário. As vezes, a “Factory” acaba adicionando complexidade indesejada. Entretanto se você estiver realizando um projeto um pouco maior ou mais complexo você pode se salvar de muitos problemas com o uso do padrão “Factory”.

### Prototype
Especifica os tipos de objetos a serem criados usando uma instância prototípica e criar novos objetos copiando este protótipo.

## Structural Patterns
> “Trabalham com a composição de classes e objetos, definindo a relação entre ambos”.

### Adapter
Converte a interface de uma classe em outra interface esperada pelos clientes. O Adapter permite que certas classes trabalhem em conjunto, pois de outra forma seria impossível por causa de suas interfaces incompatíveis.

### Bridge
Separa uma abstração da sua implementação, de modo que as duas possam variar independentemente.
Padrão extremamente utilizado para criação de temas. Imagine um site com uma quantidade de páginas onde o tema (ex: dark, green, blue) pode ser escolhido. Outro exemplo, seria uma N dispositivos utilizando N serviços de mensagem.
A ideia desse padrão seria em fazer uma ponte entre classes do tipo N->N.

### Composite
Compõe objetos em estrutura de árvore para representar hierarquias do tipo partes-todo. O Composite permite que os clientes tratem objetos individuais e composições de objetos de maneira uniforme.

### Decorator
Atribui responsabilidades adicionais a um objeto dinamicamente. Os decorators fornecem uma alternativa flexível a subclasses para extensão da funcionalidade.

Imagina a seguinte situação: Existem 3 preços praticados para venda de pipoca. A pipoca simples, pipoca com refrigerante e pipoca com chocolate. Se você precisar que uma classe seja “complemento” direto de outra no momento da instância do primeiro objeto, esse padrão se encaixa muito bem.

Importante ressaltar que o acoplamento entre classes é alta.

### Facade
Fornece uma interface unificada para um conjunto de interfaces em um subsistema. O Façade define uma interface de nível mais alto que torna o subsistema mais fácil de usar.
Usado quando um sistema é muito complexo ou difícil de entender, já que possui um grande número de classes independentes ou se trechos de código fonte estão indisponíveis. Este padrão esconde as complexidades de um sistema maior e provê uma interface simplificada

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
A fine-grained instance used for efficient sharing.
Os métodos são nomeados com o intuito de deixar a chamada mais intuitiva.
Muito utilizado para a criação de APIs onde há métodos encadeados. Outro exemplo de uso, seria uma QueryBuilder de SQL onde os atributos são encadeados. Exemplo: →where()→limit()
Outro exemplo: QueryBuilder para classe de disparo de e-mail: new Email()->from()->to()->subject()..

### Flywight
Usa compartilhamento para suportar grandes quantidades de objetos, de granularidade fina, de maneira eficiente.

### Proxy
Fornece um objeto representante (surrogate), ou um marcador de outro objeto, para controlar o acesso ao mesmo.

### Registry
Em breve...

## Behavioral Patterns
> “Definem como os objetos irão se comportar e padroniza a comunicação que haverá entre os objetos dentro da estrutura do projeto”.

### Chain of responsability
Evita o acoplamento do remetente de uma solicitação ao seu destinatário, dando a mais de um objeto a chance de tratar a solicitação. Encadeia os objetos receptores e passa a solicitação ao longo da cadeia até que um objeto a trate.

Função de evitar a dependência entre um objeto receptor e um objeto solicitante. Consiste em uma série de objetos receptores e de objetos de solicitação, onde cada objetos de solicitação possui uma lógica interna que separa quais são tipos de objetos receptores que podem ser manipulados. O restante é passado para o próximo objetos de solicitação da cadeia.

Devido à isso, é um padrão que utiliza a ideia de baixo acoplamento por permitir que outros objetos da cadeia tenham a oportunidade de tratar uma solicitação.

Cai como uma luva quando temos uma lista de comandos a serem executados de acordo com algum cenário em específico, e sabemos também qual o próximo cenário que deve ser validado, caso o anterior não satisfaça a condição.

Nesses casos, o Chain of Responsibility nos possibilita a separação de responsabilidades em classes pequenas e enxutas, e ainda provê uma maneira flexível e desacoplada de juntar esses comportamentos novamente.

### Command
Encapsula uma solicitação como um objeto, desta forma permitindo que você parametrize clientes com diferentes solicitações, enfileire ou registre (log) solicitações e suporte operações que podem ser desfeitas.

### Interpreter
Dada uma linguagem, define uma representação para sua gramática juntamente com um interpretador que usa a representação para interpretar sentenças nesta linguagem.
O padrão Interpreter é geralmente útil para interpretar DSLs.

### Interator
Cria um iterador para interagir com os objetos, retirando a iteração das responsabilidades do próprio objeto.

### Mediator
Define um objeto que encapsula como um conjunto de objetos interage. O Mediator promove o acoplamento fraco ao evitar que os objetos se refiram explicitamente uns aos outros, permitindo que você varie suas interações independentemente.

### Memento
Sem violar a encapsulação, captura e externaliza um estado interno de um objeto, de modo que o mesmo possa posteriormente ser restaurado para este estado.
Imagine, no Mind Meister por exemplo, eu colocar um nome na caixa, modificar esse nome e agora eu clico na seta da skol à esquerda para retomar a ultima ação que eu realizei. Isso é o memento. Ele grava o estado do objeto numa classe como uma espécie de “repositório” onde eu posso pegar o estado quando quiser (durante o tempo de execução daquele objeto).

### Observer
Define uma dependência um-para-muitos entre objetos, de modo que, quando um objeto muda de estado, todos os seus dependentes são automaticamente notificados e atualizados.

Sempre que uma classe precisa saber que uma ação ocorreu ou um estado foi alterado em outra classe (ou nela mesmo).

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
Permite que um objeto altere seu comportamento quando seu estado interno muda. O objeto parecerá ter mudado de classe.

### Strategy
Define uma família de algoritmos, encapsula cada um deles e os faz intercambiáveis. O Strategy permite que o algoritmo varie independentemente dos clientes que o utilizam.

Encapsula famílias específicas de algoritimos permitindo com que a classe cliente responsável por instanciar esse algoritimo em particular não necessite de conhecimento sobre sua implementação atual.

Através do encapsulamento do algoritimo, faz com que seu código de forma limpa e clara para que outros desenvolvedores possam facilmente adicionar novos tipos de saída sem que isso afete o código cliente.

### Template Method
Define o esqueleto de um algoritmo em uma operação, postergando a definição de alguns passos para subclasses. O Template Method permite que as subclasses redefinam certos passos de um algoritmo sem mudar sua estrutura.

### Visitor
Representa uma operação a ser executada sobre os elementos da estrutura de um objeto. O Visitor permite que você defina uma nova operação sem mudar as classes dos elementos sobre os quais opera, criando métodos virtualmente.

## References and read it later
* [PHP Right Way](http://br.phptherightway.com/pages/Design-Patterns.html)
* [Design Patterns PHP](http://designpatternsphp.readthedocs.io/pt_BR/latest/README.html)
* [Ocramius](https://ocramius.github.io/blog/fluent-interfaces-are-evil/) - Fluent Influence
* [Wiki](https://pt.wikipedia.org/wiki/Chain_of_Responsibility) - Chain of Responsability
* [PHP Lab](http://www.phplab.info/categories/design-pattern/template-method-pattern) - Template Method
* [PHP Lab](http://www.phplab.info/categories/design-pattern/adapter-pattern) - Adapter
* [Devmedia](https://www.devmedia.com.br/design-patterns-aplicando-os-padroes-builder-singleton-e-prototype/31023) - Builder & Singleton
* [kamranahmedse](https://github.com/kamranahmedse/design-patterns-for-humans) - Best examples For dummies
* [Stackoverflow](https://pt.stackoverflow.com/questions/106955/o-que-%c3%a9-fluent-interface) - Fluent interfaces
* [Injeção de dependência](http://fabien.potencier.org/what-is-dependency-injection.html) -
* [Composite](https://stackoverflow.com/questions/30136414/composite-pattern-and-dependency-injection) -
* [Proxy](https://www.jakowicz.com/proxy-pattern-in-php/) -
* [Specification](http://marcaube.ca/2015/05/specifications) -
* [Specification](https://en.wikipedia.org/wiki/Specification_pattern) -
* [PHP Design Patterns](https://github.com/ezimuel/PHP-design-patterns/) -
* [JavaScript Design Patterns](http://www.dofactory.com/javascript/design-patterns) -



