# PERGUNTAS DE JAVASCRIPT

## 1 - Explique com suas palavras a diferença entre a utilização de var, const e let?

**Resposta:**

**var**
- é usado para declarar uma variável (um container para alocação de dados);
- através do comando var podemos declarar variáveis de escopos de função (variáveis declaradas dentro de uma função e que só podem ser usadas dentro daquela função) e global (variáveis declaradas fora de qualquer função e que podem ser usadas em qualquer parte do código):

        var globalVariable = 'A global variable' // Escopo global

        function myFunction() {
            var functionVariable = 'A function variable' // Escopo de função
            
            console.log(globalVariable) // A global variable
            console.log(functionVariable) // A function variable
        }

        console.log(globalVariable) // A global variable
        console.log(functionVariable) // functionVariable is not defined

- se redeclararmos uma variável global dentro de uma função, alterando o seu valor, o valor dessa variável ira permanecer alterado fora daquela função:

        var name = 'Rodrigo'

        console.log(name) // Rodrigo

        function lastName() {
            var name = 'Mourão'
            
            console.log(name) // Mourão
        }

        console.log(name) // Mourão

- uma variável declarada com var pode ter seu valor redeclarado em qualquer local do código.

**let**
- assim como *var* é usado para declarar variáveis;
- contudo, além de declarar variáveis de escopos global e de função também declara variáveis de escopo de bloco (a variável é declarada dentro de um bloco de código e só pode ser acessada dentro aquele bloco);

        let x = 2 // Escopo global

        function myFunction() {
            let y = 3 // Escopo de função
            
            {
                let z = 4 // Escopo de bloco
                console.log(x) // 2
                console.log(y) // 3
                console.log(z) // 4
            }

            console.log(x) // 2
            console.log(y) // 3
            console.log(z) // block is not defined
        }

        console.log(x) // 2
        console.log(y) // local is not defined
        console.log(z) // block is not defined

- ao redeclararmos uma variável global dentro de uma função ou bloco usando *let*, se alterarmos o seu valor, essa alteração só irá valer para aquela função ou bloco de código:

        var i = 2 // Escopo global

        for (let i = 0; i < 5; i++) {
            console.log(i) // 0, 1, 2, 3, 4
        }

        console.log(i) // 2

- uma variável declarada com *let* não pode ter seu valor redeclarado com *var* ou *let* no mesmo escopo ou bloco de código;

- também não pode ter seu valor redeclarado com *var* em um escopo ou bloco de código diferente;

- entretanto, pode ter o seu valor redeclarado com *let* em um escopo ou bloco de código diferente.

**const**

- também é usado para declarar variáveis de forma similar à *let*, as principais diferenças sendo que uma variável declarada com *const* deve ter um valor atribuido em sua declaração e uma vez que seja atribuído um valor, este não pode ser reatribuído:

        const x = 5
        x = 6 // Uncaught TypeError: Assignment to constant variable.
        x = x + 5 // Uncaught TypeError: Assignment to constant variable.

        const y // Uncaught SyntaxError: Missing initializer in const declaration

- apesar do nome *const*, não define uma constante;

- é possivel incluir e alterar propriedades de um objeto declarado com *const*, porém não é possível reatribuir um o objeto:

        const pessoa = {nome: 'Fulano', sobrenome: 'Ciclano', idade: 30}
        
        pessoa.idade = 35
        
        pessoa.nacionalidade = 'Brasileiro'

        console.log(pessoa) // {nome: "Fulano", sobrenome: "Ciclano", idade: 35, nacionalidade: "Brasileiro"}

        pessoa = {nome: 'João', sobrenome: 'Silva', idade: 23, nacionalidade: 'Português'} // Uncaught TypeError: Assignment to constant variable.

- assim como acontece com objetos declarados com *const*, um vetor declarado com *const* pode receber um novo elemento ou ter um elemento alterado, mas não pode ser reatribuído;

- uma variável declarada com *const* não pode ter seu valor redeclarado por *var* ou *let* em nenhum local do código;

- entretanto pode ter o seu valor redeclarado em um escopo ou bloco de código diferente. 

***

## 2 - Assinale a(s) diferença(s) entre Funções normais e Arrow Functions.

**Opções:**

(X) Funções normais não guardam escopo

( ) Funções normais guardam escopo

( ) Arrow function são mais rápidas

( ) Arrow function podem ser instanciadas

( ) Arrow function não guardam escopo

***

## 3 - qual o valor da variável name após a execução da função?

    content = {
        name: "John",
        getName: function() {
            this.name = "James"
            return this.name
        }
    }


    userData = {
        name: "Luke",
        getName: content.getName
    }
    this.name = "Walter"
    const name = userData.getName()

**Opções:**

( ) John

( ) Luke

( ) James

(X) Walter

***

## 4 - Qual o retorno da seguinte função?

    function Event(name, day) {
        this.date = day
        this.name = name

        this.getName = function() {
            return this.name
        }
        this.getDate = function() {
            return this.date
        }
    }

    const event = new Event("04/02/2019", "Event Test")

    Event.prototype.getTitle = function() {
        return `The event ${this.name} will take place on ${this.date} `
    }
    event.getTitle()

**Opções:**

(X) The event 04/02/2019 will take place on Event Test

( ) The event undefined will take place on undefined

( ) Uncaught TypeError

( ) The event null will take place on null

***

## 5 - Quais são as formas de selecionar um elemento na DOM e qual a diferença entre elas?

**Resposta:**

***

## 6 - Como inserir um evento em determinado elemento?

**Resposta:**

***

## 7 - Como remover um evento em determinado elemento?

**Resposta:**

***

## 8 - Descreva com suas palavras o que é event bubbling?

**Resposta:**

***

## 9 - Descreva qual a diferença nos métodos de declaração de objetos?

    const object = {}
    const object = new Object()
    const object = Object.create()

**Resposta:**

***

## 10 - Qual a diferença no uso de XMLHttpRequest e Fetch? E qual devemos usar atualmente?

**Resposta:**

***

## 11 - O que são Promises? Como podemos declarar uma promise em javascript?

**Resposta:**

***

## 12 - Liste 3 formas de iterar um Array em javascript e explique a diferença entre cada um deles?

**Resposta:**

***

## 13 - Quando utilizar map, reduce ou filter?

**Resposta:**

***

## 14 - Qual o método do Array é mais indicado para remover elementos?

**Resposta:**

***

## 15 - Cite 4 métodos presentes na API de strings do Javascript e explique cada um deles.

**Resposta:**

***

## 16 - Escreva um código para inserir e resgatar items do LocalStorage/SessionStorage.

**Resposta:**

***

## 17 - Qual a melhor forma para definir um cookie utilizando javascript?

**Resposta:**

***

## 18 - Quais os tipos de Loops existentes em javascript?

**Resposta:**

***

## 19 - Descreva com suas palavras o que é hoisting?

**Resposta:**

Hoisting é o comportamento padrão do javaScript de mover, durante a interpretação do código, as declarações de variáveis para o topo/início do escopo, dessa forma variáveis declaradas com *var* podem ser usadas ou atribuídas antes de serem declaradas.

É importante lembrar que:
- hoisting só funciona com variáveis declaradas com *var*, usar ou atribuir variáveis declaradas com *let* ou *const* antes delas serem declaradas ira causar um erro;
- somente as declarações de variáveis são movidas para o início do código, as variáveis ainda precisam ser atribuídas antes que possam ser usadas;
- se o modo estrito do JavaScript estiver sendo usado (use-strict), hoisting não irá funcionar.

***

## 20 - Em um ambiente do browser. Qual o valor do this utilizando "use-strict"?

**Opções:**

( ) window

( ) global

(X) undefined

( ) null

***

## 21 - Quando eu posso utilizar o "Use-strict" no meu código?

**Opções:**

(X) No ínicio do meu código

( ) No inicio do block if

( ) No inicio de um loop

(X) no inicio de uma função

***
