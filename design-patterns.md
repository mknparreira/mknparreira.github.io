<h1>Minhas anotações | Design Patterns</h1>
<h2> Creational Patterns </h2>
<p>“In software engineering, creational design patterns are design patterns that deal with object creation mechanisms, trying to create objects in a manner suitable to the situation. The basic form of object creation could result in design problems or added complexity to the design. Creational design patterns solve this problem by somehow controlling this object creation”.</p> 
<h3>Builder</h3>
<p>Bem similar a Factory e Multition, com a diferença de que, nesse padrão, ele não somente cria objetos, mas os prepara para o restante da aplicação. Ou seja, esse padrão, define os passos para a criação de um objeto.</p>
<h3>Factory</h3>
<p>Benefícios:</p>
<ul>
  <li> Se precisar mudar, renomear ou substituir a classe Automobile futuramente você pode fazer e só terá que modificar o código na “Factory”, em vez de em todos os lugares do seu projeto onde você usa a classe Automobile. </li>
  <li> Caso a criação do objeto seja um processo complicado, você pode executar todo esse trabalho na factory, em vez de repetí-lo toda vez que precisar criar uma nova instância da classe. </li>
</ul>
<p>Usar o padrão de “Factory” não é sempre necessário. As vezes, a “Factory” acaba adicionando complexidade indesejada. Entretanto se você estiver realizando um projeto um pouco maior ou mais complexo você pode se salvar de muitos problemas com o uso do padrão “Factory”.</p>
<h2> Structural Patterns </h2>
<p>“In Software Engineering, Structural Design Patterns are Design Patterns that ease the design by identifying a simple way to realize relationships between entities”.</p>
<h3>Bridge</h3>
<p>Padrão extremamente utilizado para criação de temas. Imagine um site com uma quantidade de páginas onde o tema (ex: dark, green, blue) pode ser escolhido. Outro exemplo, seria uma N dispositivos utilizando N serviços de mensagem.</p>
<p>A ideia desse padrão seria em fazer uma ponte entre classes do tipo N->N.</p>
<h3>Composite</h3>
<p> Em breve... </p>
<h3>Decorator</h3>
<p> Adiciona novas funcionalidades a classes instanciadas dinamicamente.</p>
<p>Imagina a seguinte situação: Existem 3 preços praticados para venda de pipoca. A pipoca simples, pipoca com refrigerante e pipoca com chocolate. Se você precisar que uma classe seja “complemento” direto de outra no momento da instância do primeiro objeto, esse padrão se encaixa muito bem. Importante ressaltar que o acoplamento entre classes é alta.</p>
<h3>Injeção de dependência</h3>
<p> Em breve... </p>
<h3>Facade</h3>
<p> Em breve... </p>
<h3>Fluent Interface</h3>
<p> Os métodos são nomeados com o intuito de deixar a chamada mais intuitiva.</p>
<p>Muito utilizado para a criação de APIs onde há métodos encadeados. Outro exemplo de uso, seria uma QueryBuilder de SQL onde os atributos são encadeados. Exemplo: →where()→limit() Outro exemplo: QueryBuilder para classe de disparo de e-mail: new Email()->from()->to()->subject()..</p>
<h3>Flywight</h3>
<p> Em breve... </p>
<h3>Proxy</h3>
<p> Em breve... </p>
<h3>Registry</h3>
<p> Em breve... </p>
<h2> Behavioral Patterns </h2>
<p>“In software engineering, behavioral, design patterns that identify common communication patterns between objects and realize these patterns. By doing so, these patterns increase flexibility in carrying out this communication”.</p>
<h3>Chain of responsability</h3>
<p>Função de evitar a dependência entre um objeto receptor e um objeto solicitante. Consiste em uma série de objetos receptores e de objetos de solicitação, onde cada objetos de solicitação possui uma lógica interna que separa quais são tipos de objetos receptores que podem ser manipulados. O restante é passado para o próximo objetos de solicitação da cadeia.</p>
<p>Devido à isso, é um padrão que utiliza a ideia de baixo acoplamento por permitir que outros objetos da cadeia tenham a oportunidade de tratar uma solicitação.</p>
<p>Cai como uma luva quando temos uma lista de comandos a serem executados de acordo com algum cenário em específico, e sabemos também qual o próximo cenário que deve ser validado, caso o anterior não satisfaça a condição.</p>
<p>Nesses casos, o Chain of Responsibility nos possibilita a separação de responsabilidades em classes pequenas e enxutas, e ainda provê uma maneira flexível e desacoplada de juntar esses comportamentos novamente.</p>
<h3>Command</h3>
<p> Em breve... </p>
<h3>Interpreter</h3>
<p> O padrão Interpreter é geralmente útil para interpretar DSLs.</p>
<h3>Interator</h3>
<p> Em breve... </p>
<h3>Mediator</h3>
<p> Em breve... </p>
<h3>Memento</h3>
<p>Imagine, no Mind Meister por exemplo, eu colocar um nome na caixa, modificar esse nome e agora eu clico na seta da skol à esquerda para retomar a ultima ação que eu realizei. Isso é o memento. Ele grava o estado do objeto numa classe como uma espécie de “repositório” onde eu posso pegar o estado quando quiser (durante o tempo de execução daquele objeto).</p>
<h3>Observer</h3>
<p>Sempre que uma classe precisa saber que uma ação ocorreu ou um estado foi alterado em outra classe (ou nela mesmo).</p>
<p>Basicamente você tem dois agentes, a classe observável (conhecida como Subject) e a observadora.</p>
<p>Na classe observável você precisa ter um estado: a lista que guarda os assinantes; e três comportamentos: quem faz a adição de um novo assinante na lista, quem faz a retirada de um assinante, e quem notifica a lista de assinantes que algum evento relevante para eles ocorreu.</p>
<p>Na classe observadora você precisa de uma ação a ser realizada quando for notificado que algo que lhe interessa ocorreu.</p>
<p>Exemplos de implementação:</p>
<ul>
  <li>Um arquivo foi modificado no sistema de arquivos</li>
  <li>Uma propriedade preço foi modificada em uma classe produto</li>
  <li>Um click foi dado em botão</li>
  <li>Recebeu uma informação da rede</li>
  <li>Um objeto visual do jogo se encontrou com outro objeto (acertou o alvo)</li>
  <li>Uma atualização no banco de dados ocorreu</li>
</ul>
<h3>Proxy</h3>
<p> Em breve... </p>
<h3>Specification</h3>
<p> Em breve... </p>
<h3>State</h3>
<p> Em breve... </p>
<h3>Strategy</h3>
<p> Encapsula famílias específicas de algoritimos permitindo com que a classe cliente responsável por instanciar esse algoritimo em particular não necessite de conhecimento sobre sua implementação atual. </p>
<p>Através do encapsulamento do algoritimo, faz com que seu código de forma limpa e clara para que outros desenvolvedores possam facilmente adicionar novos tipos de saída sem que isso afete o código cliente.</p>
<h3>Template Method</h3>
<p> Em breve... </p>
<h3>Visitor</h3>
<p> Em breve... </p>
<h2> References </h2>
<p>http://br.phptherightway.com/pages/Design-Patterns.html</p>
<p>http://designpatternsphp.readthedocs.io/pt_BR/latest/README.html</p>
<p>https://ocramius.github.io/blog/fluent-interfaces-are-evil/</p>
<p>https://pt.wikipedia.org/wiki/Chain_of_Responsibility</p>
<p>http://www.phplab.info/categories/design-pattern/template-method-pattern</p>
<p>http://www.phplab.info/categories/design-pattern/adapter-pattern</p>
<p>https://www.devmedia.com.br/design-patterns-aplicando-os-padroes-builder-singleton-e-prototype/31023</p>
<p>https://github.com/kamranahmedse/design-patterns-for-humans</p>
<p>https://pt.stackoverflow.com/questions/106955/o-que-%c3%a9-fluent-interface</p>

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

