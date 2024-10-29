# JavaScript

**Minhas anotações**

## Template String

Template strings são definidas usando crases **(`)** em vez de aspas simples **(')** ou duplas **(")**.

**Interpolação de Variáveis**

```javacript
  const nome = "João";
  const idade = 25;
  const mensagem = `Meu nome é ${nome} e eu tenho ${idade} anos.`;
  console.log(mensagem); // "Meu nome é João e eu tenho 25 anos."
```

---

## Operador Ternário


O operador ternário em JavaScript é uma forma concisa de fazer uma verificação condicional. Ele funciona como um atalho para a estrutura if...else

**Sintaxe**

```javascript
  condição ? valorSeVerdadeiro : valorSeFalso;

```

- **Condição:** Uma expressão que será avaliada como verdadeira ou falsa.
- **Valor se verdadeiro:** O valor que será retornado se a condição for verdadeira.
- **Valor se falso:** O valor que será retornado se a condição for falsa.

```javascript
  let idade = 18;
  let podeDirigir = (idade >= 18) ? "Sim" : "Não";
  
  console.log(podeDirigir); // Saída: "Sim"

```

**Explicação**

- **Condição:** idade >= 18
- Se a condição for verdadeira, **podeDirigir** será **"Sim"**.
- Se for falsa, **podeDirigir** será **"Não"**.

---

## Math


O objeto Math em JavaScript é uma coleção de propriedades e métodos matemáticos que você pode usar para realizar cálculos. Aqui estão alguns dos principais recursos do objeto Math e como usá-los:

### Propriedades do Math

- **Math.PI:** O valor de π (pi), aproximadamente 3.14159.

- **Math.E:** O valor de e (base do logaritmo natural), aproximadamente 2.71828.

### Métodos do Math

- **Math.abs(x):** Retorna o valor absoluto de x.
```javascript
  console.log(Math.abs(-5)); // 5
```
- **Math.ceil(x):** Arredonda x para cima.
```javascript
  console.log(Math.ceil(4.2)); // 5
```
- **Math.floor(x):** Arredonda x para baixo.
```javascript
  console.log(Math.floor(4.7)); // 4
```
- **Math.round(x):** Arredonda x para o inteiro mais próximo.
```javascript
  console.log(Math.round(4.5)); // 5
```
- **Math.random():** Retorna um número pseudo-aleatório entre 0 (inclusive) e 1 (exclusivo).
```javascript
  console.log(Math.random()); // Um número aleatório entre 0 e 1
```
- **Math.max(...values):** Retorna o maior valor entre os argumentos.
```javascript
  console.log(Math.max(1, 2, 3)); // 3
```
- **Math.min(...values):** Retorna o menor valor entre os argumentos.
```javascript
  console.log(Math.min(1, 2, 3)); // 1
```
- **Math.pow(base, exponent):** Retorna a base elevada à potência do expoente.
```javascript
  console.log(Math.pow(2, 3)); // 8
```
- **Math.sqrt(x):** Retorna a raiz quadrada de x.
```javascript
  console.log(Math.sqrt(16)); // 4
```
- **Math.sin(x)**, **Math.cos(x)**, **Math.tan(x):** Retornam o seno, cosseno e tangente de x (em radianos).
```javascript
  console.log(Math.sin(Math.PI / 2)); // 1
  console.log(Math.cos(Math.PI));    // -1
```

---

## Destructuring

O destructuring (ou destruturação) é um recurso do JavaScript que permite extrair valores de arrays ou propriedades de objetos em variáveis distintas de forma mais concisa e legível.

**Conceito**

A destruturação facilita a extração de dados, reduzindo a quantidade de código necessária para acessar elementos de arrays ou propriedades de objetos. Em vez de acessar cada item ou propriedade individualmente, você pode fazer isso em uma única linha, o que torna o código mais claro e direto.

```javascript

const pessoa = {
  nome: 'Alice',
  idade: 25,
  cidade: 'São Paulo'
};

// Sem destructuring
const nome = pessoa.nome;
const idade = pessoa.idade;

// Com destructuring
const { nome, idade } = pessoa;

console.log(nome); // 'Alice'
console.log(idade); // 25

```

Você também pode renomear as variáveis ao fazer a destruturação:

```javascript

const { nome: nomeCompleto, idade: anos } = pessoa;

console.log(nomeCompleto); // 'Alice'
console.log(anos); // 25

```
**Destructuring de Arrays**

A destruturação de arrays é semelhante. Você pode extrair elementos do array em variáveis separadas:

```javascript

const numeros = [1, 2, 3];

// Sem destructuring
const primeiro = numeros[0];
const segundo = numeros[1];

// Com destructuring
const [primeiro, segundo] = numeros;

console.log(primeiro); // 1
console.log(segundo); // 2

```

Você também pode ignorar elementos durante a destruturação:

```javascript

const [um, , tres] = numeros;

console.log(um); // 1
console.log(tres); // 3

```

**Vantagens do Destructuring**

1. **Legibilidade:** O código se torna mais fácil de ler e entender.
2. **Menos código:** Você escreve menos código para obter os mesmos resultados.
3. **Flexibilidade:** Permite que você renomeie variáveis facilmente.

---

## Operador spread

O **spread operator** (operador de espalhamento) em JavaScript é representado por três pontos (...) e é usado para expandir ou "espalhar" elementos de um array ou propriedades de um objeto em um novo contexto. Ele é bastante útil para copiar arrays ou objetos, combinar dados e passar argumentos em funções

**Exemplos de Uso**

- Espalhando Elementos de um Array
Você pode usar o spread operator para criar uma cópia de um array ou para combinar arrays:
```javascript

const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

// Copiando um array
const arrayCopy = [...array1];
console.log(arrayCopy); // [1, 2, 3]

// Combinando arrays
const combinedArray = [...array1, ...array2];
console.log(combinedArray); // [1, 2, 3, 4, 5, 6]

```

- Espalhando Propriedades de um Objeto
O spread operator também pode ser usado com objetos para copiar ou combinar propriedades:

```javascript
const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };

// Copiando um objeto
const objCopy = { ...obj1 };
console.log(objCopy); // { a: 1, b: 2 }

// Combinando objetos
const combinedObj = { ...obj1, ...obj2 };
console.log(combinedObj); // { a: 1, b: 3, c: 4 }

```

Note que, ao combinar objetos, se houver propriedades com o mesmo nome, a última sobrescreverá as anteriores.

- Passando Argumentos para Funções
O spread operator pode ser utilizado para passar elementos de um array como argumentos para uma função:

```javascript

const numbers = [1, 2, 3];

function sum(a, b, c) {
  return a + b + c;
}

// Usando o spread operator
const result = sum(...numbers);
console.log(result); // 6

```

---

## JSON


JSON é um formato baseado em pares de chave-valor. Por exemplo:

```javascript
{
  "nome": "João",
  "idade": 30,
  "email": "joao@example.com"
}
```

---

## Funções-JavaScript

**Minhas anotações**

Uma função é um bloco de código projetado para executar uma tarefa específica. Você pode chamar uma função sempre que precisar executar essa tarefa.

**Declaração de Funções**

1. **Função Declarada (Function Declaration)**

```javascript

function saudacao(nome) {
    return `Olá, ${nome}!`;
}

console.log(saudacao("Maria")); // Saída: Olá, Maria!

```

2. **Função Anônima (Function Expression)**

```javascript

const somar = function(a, b) {
    return a + b;
};

console.log(somar(5, 3)); // Saída: 8

```

3. **Arrow Function (Função de seta)**

```javascript

const multiplicar = (x, y) => x * y;

console.log(multiplicar(4, 5)); // Saída: 20

```

**Parâmetros e Argumentos**

- **Parâmetros** são as variáveis que você define na declaração da função.
- **Argumentos** são os valores que você passa para a função quando a chama.

```javascript

function exibirMensagem(mensagem) {
    console.log(mensagem);
}

exibirMensagem("Aprendendo JavaScript!"); // Saída: Aprendendo JavaScript!

```

**Retorno de Funções**

Uma função pode retornar um valor usando a palavra-chave return. Quando uma função retorna um valor, você pode usá-lo na expressão que chamou a função.

```javascript

function calcularArea(base, altura) {
    return (base * altura) / 2;
}

const area = calcularArea(5, 10);
console.log(area); // Saída: 25

```

**Funções como Objetos**

Em JavaScript, funções são objetos de primeira classe, o que significa que podem ser atribuídas a variáveis, passadas como argumentos e retornadas de outras funções.

```javascript

function executar(funcao) {
    funcao();
}

executar(() => console.log("Função executada!")); // Saída: Função executada!

```

**Funções Recursivas**

Uma função pode chamar a si mesma. Isso é conhecido como recursão.

```javascript

function fatorial(n) {
    if (n === 0) {
        return 1;
    }
    return n * fatorial(n - 1);
}

console.log(fatorial(5)); // Saída: 120

```

### Métodos nativos úteis para se trabalhar com funções.

- **call()**
  
Invoca uma função com um valor específico para this e argumentos passados individualmente.

```javascript

function greet() {
  console.log(`Olá, ${this.name}`);
}

const person = { name: 'Maria' };
greet.call(person); // Olá, Maria

```

- **apply()**
  
Funciona de maneira semelhante ao call(), mas aceita um array de argumentos em vez de argumentos individuais.

```javascript

function sum(a, b) {
  return a + b;
}

const numbers = [3, 5];
console.log(sum.apply(null, numbers)); // 8

```
- **bind()**

Cria uma nova função que, quando chamada, tem o valor de this definido para o primeiro argumento passado e os demais argumentos pré-definidos.

```javascript

const person = { name: 'Lucas' };

function greet() {
  console.log(`Olá, ${this.name}`);
}

const greetLucas = greet.bind(person);
greetLucas(); // Olá, Lucas

```

- **arrow functions**

Uma sintaxe mais concisa para declarar funções. Elas têm um comportamento léxico para this, ou seja, this refere-se ao contexto de onde a função foi criada.

```javascript

const soma = (a, b) => a + b;
console.log(soma(2, 3)); // 5

```

- **setTimeout()**

Executa uma função após um intervalo de tempo especificado.

```javascript

setTimeout(() => {
  console.log('Isso será executado após 2 segundos');
}, 2000);

```

- **setInterval()**

Executa uma função repetidamente a cada intervalo de tempo especificado.

```javascript

setInterval(() => {
  console.log('Isso será executado a cada 2 segundos');
}, 2000);

```

- **clearTimeout()**

Cancela uma função agendada via setTimeout().

```javascript

const timer = setTimeout(() => console.log('Isso não será mostrado'), 2000);
clearTimeout(timer);

```

- **clearInterval()**

Cancela uma função repetitiva agendada via setInterval().

```javascript

const intervalId = setInterval(() => console.log('Repetindo'), 1000);
clearInterval(intervalId); // Interrompe o intervalo

```
- preventDefault()

preventDefault é um método em JavaScript usado para evitar o comportamento padrão de um evento. 

Exemplo em um formulário: 

```javascript

const handleSubmit = (event) => {
  event.preventDefault(); // Impede o envio do formulário
  console.log("Formulário não enviado");
};

```

- **Function.prototype.toString()**

Retorna o código fonte de uma função em formato de string.

```javascript

function exemplo() {
  return 'Exemplo';
}

console.log(exemplo.toString());

```

- **Function.prototype.length**

Retorna o número de parâmetros declarados na função.

```javascript

function soma(a, b) {}
console.log(soma.length); // 2

```

- **Function.prototype.name**
  
Retorna o nome da função (útil para depuração).

```javascript

function exemplo() {}
console.log(exemplo.name); // exemplo

```

- **arguments**

Um objeto semelhante a um array que contém os argumentos passados para a função. Disponível em funções tradicionais, mas não em arrow functions.

```javascript

function sum() {
  let total = 0;
  for (let i = 0; i < arguments.length; i++) {
    total += arguments[i];
  }
  return total;
}

console.log(sum(1, 2, 3, 4)); // 10

```

- **Function constructor**
  
Permite criar uma função dinamicamente a partir de uma string. Porém, seu uso não é recomendado por questões de segurança e desempenho.

```javascript

const soma = new Function('a', 'b', 'return a + b');
console.log(soma(2, 3)); // 5

```

- **typeof**

Operador que retorna o tipo de uma função.

```javascript

function exemplo() {}
console.log(typeof exemplo); // "function"

```

- **instanceof**

Verifica se uma função foi criada a partir de uma determinada classe ou construtor.

```javascript

function MinhaFuncao() {}

const obj = new MinhaFuncao();
console.log(obj instanceof MinhaFuncao); // true

```

- **includes()**

Verifica se um array ou uma string contém um determinado valor. Ele retorna true se o valor for encontrado e false caso contrário.

```javascript

const frutas = ['maçã', 'banana', 'laranja'];

console.log(frutas.includes('banana')); // true
console.log(frutas.includes('uva'));    // false

```

Esses métodos fornecem uma base sólida para trabalhar com funções em JavaScript, desde a manipulação básica até técnicas mais avançadas, como controle de contexto e agendamento de execução.

---

## Orientação a Objeto-JavaScript

**Minhas anotações**

Um objeto é uma coleção de propriedades, onde cada propriedade é uma associação entre uma chave (ou nome) e um valor. Os valores podem ser de qualquer tipo, incluindo outros objetos, funções (que são chamadas de métodos quando associadas a um objeto) e tipos primitivos.

### Funções importantes da classe ***Object***

#### Object.keys(obj)

A função **Object.keys(obj)** é um método em JavaScript que retorna um array contendo as chaves (propriedades enumeráveis) de um objeto

**Sintaxe**

```javascript

Object.keys(obj)

```

**Retorno**

Retorna um array contendo as chaves enumeráveis do objeto. Se o objeto não tiver propriedades enumeráveis, retorna um array vazio.

**Exemplo**

```javascript
const pessoa = {
    nome: 'João',
    idade: 30,
    cidade: 'São Paulo'
};

const chaves = Object.keys(pessoa);
console.log(chaves); // ['nome', 'idade', 'cidade']

```

#### Object.values(obj)

A função **Object.values(obj)** é um método em JavaScript que retorna um array contendo os valores das propriedades enumeráveis de um objeto.

**Sintaxe**

```javascript

Object.values(obj)

```

**Retorno**

Retorna um array com os valores das propriedades enumeráveis do objeto. Se o objeto não tiver propriedades enumeráveis, retorna um array vazio.

**Exemplo**

```javascript

const pessoa = {
    nome: 'João',
    idade: 30,
    cidade: 'São Paulo'
};

const valores = Object.values(pessoa);
console.log(valores); // ['João', 30, 'São Paulo']

```

#### Object.entries(obj)

A função **Object.entries(obj)** é um método em JavaScript que retorna um array de arrays, onde cada sub-array contém um par chave-valor de um objeto.

**Sintaxe**

```javascript

Object.entries(obj)

```

**Retorno**

Retorna um array de arrays, onde cada sub-array contém dois elementos: a chave e o valor correspondente. Se o objeto não tiver propriedades enumeráveis, retorna um array vazio.

**Exemplo**

```javascript

const pessoa = {
    nome: 'João',
    idade: 30,
    cidade: 'São Paulo'
};

const entradas = Object.entries(pessoa);
console.log(entradas); 
// [['nome', 'João'], ['idade', 30], ['cidade', 'São Paulo']]

```

#### Object.defineProperty(obj, prop, descriptor)

A função **Object.defineProperty(obj, prop, descriptor)** é um método em JavaScript que permite definir uma nova propriedade em um objeto ou modificar uma propriedade existente, configurando atributos específicos dessa propriedade através de um objeto de descritor.

**Sintaxe**

```javascript

Object.defineProperty(obj, prop, descriptor)

```

- obj: O objeto no qual a propriedade será definida ou modificada.
- prop: O nome da propriedade a ser definida ou modificada.
- descriptor: Um objeto que descreve a propriedade e pode conter os seguintes atributos:



**Atributos do Descritor**

1. value: O valor da propriedade.
2. writable: Um booleano que indica se a propriedade pode ser modificada. O padrão é false.
3. enumerable: Um booleano que indica se a propriedade aparece durante a iteração sobre as propriedades do objeto. O padrão é false.
4. configurable: Um booleano que indica se a propriedade pode ser deletada ou se suas características (como writable e enumerable) podem ser alteradas. O padrão é false.

**Exemplo**

```javascript

const pessoa = {};

Object.defineProperty(pessoa, 'nome', {
    value: 'João',
    writable: false,   // Não pode ser modificado
    enumerable: true,  // Pode ser enumerado
    configurable: true // Pode ser configurado
});

console.log(pessoa.nome); // 'João'

pessoa.nome = 'Maria'; // Não faz nada, pois writable é false
console.log(pessoa.nome); // 'João'

for (let chave in pessoa) {
    console.log(chave); // 'nome'
}

delete pessoa.nome; // Pode ser deletado, pois configurable é true
console.log(pessoa.nome); // undefined

```

#### Object.assign(target, ...sources)

O **Object.assign** é um método que é usado para copiar as propriedades de um ou mais objetos para um objeto de destino. Ele é muito útil para a criação de novos objetos a partir de objetos existentes, facilitando a combinação de propriedades e a criação de cópias de objetos.

**Sintaxe**

```javascript

Object.assign(destino, ...fontes);

```

1. destino: O objeto que receberá as propriedades.
2. ...fontes: Um ou mais objetos cujas propriedades serão copiadas para o objeto de destino.

**Exemplo**

```javascript
const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };

const resultado = Object.assign({}, obj1, obj2);
console.log(resultado); // { a: 1, b: 3, c: 4 }

```

#### Object.freeze(obj)

A função **Object.freeze(obj)** é um método em JavaScript que congela um objeto, tornando-o imutável. Isso significa que você não pode adicionar, remover ou modificar suas propriedades depois que o objeto foi congelado.

**Sintaxe**

```javascript

Object.freeze(obj)

```
**Comportamento**

  1. **Imutabilidade:** Depois de congelado, um objeto não pode ter novas propriedades adicionadas, propriedades existentes não podem ser removidas ou modificadas (mesmo que suas propriedades sejam objetos).
  2. **Propriedades Não Enumeráveis:** O método não afeta as propriedades não enumeráveis de um objeto. Se o objeto já tiver propriedades não enumeráveis, elas permanecerão inalteradas.
  3. **Níveis de Congelamento:** Apenas o objeto em si é congelado. Se ele contém objetos aninhados, essas propriedades aninhadas ainda podem ser alteradas a menos que também sejam congeladas.

**Exemplo**

```javascript

const pessoa = {
    nome: 'João',
    idade: 30
};

Object.freeze(pessoa);

pessoa.idade = 31; // Não fará nada
pessoa.cidade = 'São Paulo'; // Não fará nada
delete pessoa.nome; // Não fará nada

console.log(pessoa); // { nome: 'João', idade: 30 }

```

#### Object.seal(obj)

A **função Object.seal(obj)** é um método em JavaScript que "sele" um objeto, permitindo que suas propriedades existentes sejam modificadas, mas impedindo que novas propriedades sejam adicionadas ou que propriedades existentes sejam removidas. 

**Sintaxe**

```javascript

Object.seal(obj)

```

**Comportamento**

1. **Imutabilidade Estrutural:** Depois que um objeto é selado, você não pode adicionar novas propriedades ou remover as existentes. No entanto, você ainda pode modificar os valores das propriedades existentes, desde que elas sejam enumeráveis
2. **Propriedades Não Enumeráveis:** O método não afeta as propriedades não enumeráveis de um objeto. Se o objeto já tiver propriedades não enumeráveis, elas permanecerão inalteradas.
3. **Propriedades Existentes:** Você pode modificar as propriedades existentes, mesmo que estejam seladas.

**Exemplo**

```javascript

const pessoa = {
    nome: 'João',
    idade: 30
};

Object.seal(pessoa);

pessoa.idade = 31; // Permite a modificação
pessoa.cidade = 'São Paulo'; // Não permite a adição
delete pessoa.nome; // Não permite a remoção

console.log(pessoa); // { nome: 'João', idade: 31 }

```

#### Object.getOwnPropertyNames(obj)

A **função Object.getOwnPropertyNames(obj)** é um método em JavaScript que retorna um array contendo os nomes (chaves) de todas as propriedades de um objeto, tanto as enumeráveis quanto as não enumeráveis. 

```javascript

Object.getOwnPropertyNames(obj)

```

**Retorno**

Retorna um array com os nomes de todas as propriedades do objeto. Se o objeto não tiver propriedades, retorna um array vazio.

**Exemplo**

```javascript

const pessoa = {
    nome: 'João',
    idade: 30
};

Object.defineProperty(pessoa, 'cpf', {
    value: '123.456.789-00',
    enumerable: false // Não enumerável
});

const propriedades = Object.getOwnPropertyNames(pessoa);
console.log(propriedades); // ['nome', 'idade', 'cpf']

```
  
#### Object.getPrototypeOf(obj)

A função Object.getPrototypeOf(obj) é um método em JavaScript que retorna o protótipo do objeto especificado. O protótipo é o objeto a partir do qual o objeto dado herda suas propriedades e métodos.

**Sintaxe**

```javascript

Object.getPrototypeOf(obj)

```
**Retorno**

Retorna o protótipo do objeto especificado. Se o objeto não tiver um protótipo (como um objeto criado com Object.create(null)), o método retornará null.

**Exemplo**

```javascript

const pessoa = {
    nome: 'João',
    idade: 30
};

const prototipo = Object.getPrototypeOf(pessoa);
console.log(prototipo); // { ... } (prototipo padrão do objeto)

```

---

## Array-JavaScript

**Minhas anotações**

Um array é uma estrutura de dados que permite armazenar múltiplos valores em uma única variável. Os elementos de um array podem ser de diferentes tipos, como números, strings, objetos e até outros arrays.

**Como criar um array**

- Usando colchetes[]:

```javascript

const frutas = ['maçã', 'banana', 'laranja'];

```

- Usando o construtor Array:

```javascript

const numeros = new Array(1, 2, 3, 4, 5);

```

### Métodos importantes para manipular e interagir com um array

#### Métodos de Manipulação de Arrays

- **push():** Adiciona um ou mais elementos ao final de um array e retorna o novo comprimento do array.

```javacript

const arr = [1, 2, 3];
arr.push(4); // arr é [1, 2, 3, 4]

```

- **pop():** Remove o último elemento de um array e o retorna. Esse método altera o comprimento do array.

```javacript

const arr = [1, 2, 3];
arr.pop(); // arr é [1, 2]

```

- **shift():** Remove o primeiro elemento de um array e o retorna, alterando o comprimento do array.

```javacript

const arr = [1, 2, 3];
arr.shift(); // arr é [2, 3]

```

- **unshift():** Adiciona um ou mais elementos ao início de um array e retorna o novo comprimento do array.

```javacript

const arr = [1, 2, 3];
arr.unshift(0); // arr é [0, 1, 2, 3]

```

#### Métodos de Iteração

- **forEach():** Executa uma função fornecida uma vez para cada elemento do array.

```javacript

const arr = [1, 2, 3];
arr.forEach(num => console.log(num));

```

- **map():** Cria um novo array com os resultados da chamada de uma função para cada elemento do array.

```javacript

const arr = [1, 2, 3];
const doubled = arr.map(num => num * 2); // [2, 4, 6]

```

- **filter():** Cria um novo array com todos os elementos que passam no teste implementado pela função fornecida.

```javacript

const arr = [1, 2, 3, 4];
const evens = arr.filter(num => num % 2 === 0); // [2, 4]

```

- **reduce():** Executa uma função redutora em cada elemento do array, resultando em um único valor.

```javacript

const arr = [1, 2, 3];
const sum = arr.reduce((acc, curr) => acc + curr, 0); // 6

```

#### Métodos de Busca e Localização

- **find():** Retorna o valor do primeiro elemento do array que satisfaz a função de teste fornecida.

```javacript

const arr = [1, 2, 3, 4];
const found = arr.find(num => num > 2); // 3

```

- **indexOf():** Retorna o primeiro índice em que um determinado elemento pode ser encontrado no array, ou -1 se não estiver presente.

```javacript

const arr = [1, 2, 3];
const index = arr.indexOf(2); // 1

```

#### Métodos de Ordenação e Modificação

- **sort():** Ordena os elementos do array in-place e retorna o array. O método pode tomar uma função de comparação como argumento.

```javacript

const arr = [3, 1, 2];
arr.sort(); // [1, 2, 3]

```

- **reverse():** Inverte a ordem dos elementos do array.

```javacript

const arr = [1, 2, 3];
arr.reverse(); // [3, 2, 1]

```

#### Métodos de Criação de Novos Arrays
  
- **slice():** Retorna uma cópia rasa de uma parte do array em um novo array.

```javacript

const arr = [1, 2, 3, 4];
const sliced = arr.slice(1, 3); // [2, 3]

```

- **splice():** Altera o conteúdo de um array removendo ou substituindo elementos existentes e/ou adicionando novos elementos.

```javacript

const arr = [1, 2, 3, 4];
arr.splice(1, 2, 5); // arr é [1, 5, 4]

```

#### Outros

- **concat():** Usado para unir dois ou mais arrays. Este método não altera os arrays existentes, mas retorna um novo array.

```javacript

const arr1 = [1, 2];
const arr2 = [3, 4];
const combined = arr1.concat(arr2); // [1, 2, 3, 4]

```

---

## Promise


Uma promessa é um objeto que representa a eventual conclusão ou falha de uma operação assíncrona e seu valor resultante. Ela pode estar em um dos seguintes estados:

- **Pendente (Pending)**: Estado inicial, quando a operação ainda não foi concluída.
- **Cumprida (Fulfilled)**: A operação foi concluída com sucesso.
- **Rejeitada (Rejected)**: A operação falhou.

---

## sessionStorage


é uma **API** de armazenamento web do JavaScript, que permite armazenar dados no navegador do usuário. A principal característica do sessionStorage é que ele mantém os dados apenas durante a sessão do navegador. Isso significa que os dados armazenados nele estão disponíveis enquanto a aba ou janela do navegador estiver aberta, mas serão perdidos assim que a aba for fechada.

---

## localStorage


O localStorage é outra **API** de armazenamento web do JavaScript, que permite armazenar dados no navegador do usuário de forma persistente. Ao contrário do sessionStorage, os dados armazenados no localStorage permanecem disponíveis mesmo após o fechamento da aba ou do navegador, até que sejam explicitamente removidos.

---


# Dominando-o-React

Aqui deixarei minhas anotações do estudo da biblioteca React

---

# O que é o React?

O React é uma biblioteca JavaScript desenvolvida pelo Facebook para construir interfaces de usuário, especialmente em aplicações web. Ele permite criar componentes reutilizáveis, o que facilita o desenvolvimento e a manutenção de grandes aplicações. O React utiliza uma abordagem declarativa, o que significa que você descreve como a interface deve se parecer em diferentes estados, e ele cuida de atualizar a DOM de forma eficiente.

---

## npm

O **npm (Node Package Manager)** é um gerenciador de pacotes para o ambiente *Node.js*. Ele permite que você instale, atualize e gerencie bibliotecas e dependências de *JavaScript* em seus projetos. O npm é uma ferramenta essencial para desenvolvedores que trabalham com *JavaScript*, pois facilita a inclusão de pacotes de código já prontos, como o *React* e suas dependências.

### Aqui estão algumas funcionalidades principais do npm:

- **Instalação de Pacotes:** Você pode instalar pacotes de forma simples, usando o comando npm install nome-do-pacote. Isso adiciona a biblioteca ao seu projeto e a lista de dependências no arquivo package.json.

- **Gerenciamento de Dependências:** O package.json é um arquivo que contém informações sobre seu projeto, incluindo as dependências que ele usa. O npm lê esse arquivo para instalar as versões corretas dos pacotes.

- **Scripts:** O npm permite que você defina scripts personalizados no package.json, que podem ser executados com comandos como npm run nome-do-script. Isso é útil para automação de tarefas, como iniciar um servidor de desenvolvimento ou executar testes.

- **Publicação de Pacotes:** Você também pode criar e publicar seus próprios pacotes no repositório npm, tornando-os disponíveis para a comunidade.

Ao iniciar um projeto com React, você normalmente usará o npm para instalar o React e suas bibliotecas associadas.

---

## JSX

**JSX** é uma extensão de sintaxe para JavaScript que permite escrever elementos HTML dentro do JavaScript. Ele é frequentemente usado em aplicações React para descrever como a interface de usuário deve parecer.

### Aqui estão alguns pontos chave sobre JSX:

- **Sintaxe Similar ao HTML:** Com JSX, você pode escrever código que se parece muito com HTML. Por exemplo:

```javascript

const element = <h1>Olá, mundo!</h1>;

```
- **JavaScript Dentro do JSX:** Você pode inserir expressões JavaScript dentro de chaves {}, as expressões dentro das chaves {} são chamadas de "template expressions". Por exemplo:

```javascript

const nome = "João";
const element = <h1>Olá, {nome}!</h1>;

```

- **Componentes:** JSX é frequentemente usado para criar componentes React. Um componente pode retornar JSX para renderizar na interface. Por exemplo:

```javascript

function MeuComponente() {
    return <h1>Olá, mundo!</h1>;
}

```

- **Atributos:** Você pode passar atributos para elementos JSX da mesma forma que faria em HTML, mas algumas vezes a nomenclatura muda. Por exemplo, class em HTML se torna className em JSX:

```javascript

const element = <div className="minha-classe">Conteúdo</div>;

```

- **Compilação:** O JSX não é compreendido pelo navegador diretamente, então ele precisa ser transformado em JavaScript puro. Isso geralmente é feito por ferramentas como Babel, que é configurado em ambientes de desenvolvimento React.

- **Fragmentos:** Se você quiser retornar múltiplos elementos sem adicionar um nó pai extra no DOM, você pode usar fragmentos:

```javascript

return (
    <>
        <h1>Título</h1>
        <p>Parágrafo</p>
    </>
);

```

---

## Hooks

Hooks são funções que permitem que você "conecte" o estado (*states*) e outras funcionalidades do React a componentes funcionais.

#### estado (*state*)

Em React, "estado" refere-se a dados que podem mudar ao longo do tempo. Quando o estado de um componente muda, o React re-renderiza o componente para refletir essas mudanças.

#### Previous states

No React, cada componente pode ter um estado interno que controla suas características e comportamento. Quando você atualiza o estado de um componente, o React pode precisar saber qual era o estado anterior para calcular o novo estado ou para garantir que a atualização ocorra da maneira esperada. Isso é especialmente importante em situações onde o novo estado depende do estado anterior.

#### Exemplo com Functional Components e Hooks

Você pode usar o hook useState e a função de atualização pode receber uma função que aceita o estado anterior.

```javascript

import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount((prevCount) => prevCount + 1);
  };

  return (
    <div>
      <p>Contador: {count}</p>
      <button onClick={increment}>Incrementar</button>
    </div>
  );
};

```

---

### useState

**Como utilizar adequadamente o *useState* em React**

O useState é um [hook](#Hooks) em React que permite adicionar e gerenciar estado em componentes funcionais. Ele retorna um array com dois elementos: o valor do estado atual e uma função para atualizar o estado.

**Sintaxe básica:**

```javascript

const [estado, setEstado] = useState(valorInicial);

```
- **estado:** O valor atual do estado.
- **setEstado:** Função usada para atualizar o valor do estado.
- **useState(valorInicial):** Inicializa o estado com valorInicial.

**Exemplo básico:**

```javascript

import React, { useState } from 'react';

function Contador() {
  const [contador, setContador] = useState(0); // Inicia o estado com 0

  return (
    <div>
      <p>Você clicou {contador} vezes</p>
      <button onClick={() => setContador(contador + 1)}>
        Aumentar Contador
      </button>
    </div>
  );
}

```

**Explicação:**

1. const [contador, setContador] = useState(0);: Define uma variável de estado contador com valor inicial 0 e uma função setContador para atualizar esse estado.
2. setContador(contador + 1): Atualiza o valor do estado contador somando 1 ao valor atual quando o botão for clicado.

**Atualização do estado**

- **Substituição do valor:** O valor passado para a função de atualização (setEstado) substitui o valor anterior.

**Exemplo:**

```javascript

setContador(5); // O valor de contador agora é 5

```

- **Função de atualização:** Ao invés de passar diretamente o novo valor, você pode passar uma função para setEstado. Isso é útil quando o novo estado depende do valor anterior.

**Exemplo:**

```javascript

setContador((contadorAnterior) => contadorAnterior + 1);

```

Nesse caso, setContador acessa o valor anterior (contadorAnterior) e o incrementa.

**Estado inicial dinâmico**

Você pode usar uma função como argumento de useState para calcular o valor inicial apenas na primeira renderização. Isso é útil para cálculos mais complexos que não precisam ser reexecutados em cada renderização.

**Exemplo:**

```javascript

const [contador, setContador] = useState(() => calcularValorInicial());

```

Aqui, calcularValorInicial() só será chamado na primeira vez que o componente for montado.

**Boas práticas ao usar *useState***

1. **Atualizações de estado são assíncronas:** O React não atualiza o estado instantaneamente. Ele "agenda" a atualização, e a nova renderização do componente ocorre na próxima execução do ciclo de vida.

2. **Imutabilidade:** Sempre retorne um novo valor para o estado, e não modifique diretamente o estado anterior. Por exemplo, com objetos ou arrays, sempre crie uma cópia atualizada ao invés de alterar o original.

**Exemplo:**

```javascript

setLista([...lista, novoItem]); // Cria uma nova lista adicionando o novo item

```

3. **Gerenciar múltiplos estados:** Para estados que precisam ser tratados separadamente, é possível usar useState várias vezes no mesmo componente.

**Exemplo:**

```javascript

const [nome, setNome] = useState('');
const [idade, setIdade] = useState(0);

```

4. Evite usar objetos complexos quando possível: Se o estado pode ser mantido como uma variável simples (números, strings, booleans), prefira esse formato ao invés de usar objetos, para facilitar as atualizações e evitar bugs.

---

### useEffect

**Como utilizar adequadamente o *useEffect* em React**

O useEffect é um [hook](#Hooks) que permite realizar efeitos colaterais em componentes funcionais. Efeitos colaterais são operações que ocorrem fora do fluxo de renderização principal, como buscar dados de uma API, manipular o DOM diretamente, ou configurar timers.

**Sintaxe básica:**

```javascript

useEffect(() => {
  // Código do efeito colateral
  return () => {
    // Função de limpeza opcional
  };
}, [dependencias]);

```

- **Função principal:** O primeiro argumento do useEffect é uma função que será executada após o componente ser renderizado.
- **Função de limpeza (opcional):** Retornar uma função dentro do useEffect permite realizar uma "limpeza" (como cancelar assinaturas ou limpar timers) quando o componente for desmontado ou o efeito for reexecutado.
- **Array de dependências:** O segundo argumento é um array que define quando o efeito será executado. Ele indica as variáveis que, quando alteradas, irão disparar a execução do efeito novamente.

**Exemplo básico:**

```javascript

import React, { useEffect, useState } from 'react';

function Componente() {
  const [contador, setContador] = useState(0);

  useEffect(() => {
    document.title = `Você clicou ${contador} vezes`;

    return () => {
      console.log("Limpeza realizada"); // Exemplo de limpeza
    };
  }, [contador]); // O efeito será executado quando "contador" mudar

  return (
    <div>
      <p>Você clicou {contador} vezes</p>
      <button onClick={() => setContador(contador + 1)}>
        Aumentar Contador
      </button>
    </div>
  );
}

```

**Explicação:**

1. **Efeito colateral:** O título da página (document.title) é atualizado sempre que o valor de contador muda.
2. **Dependências:** O efeito será reexecutado sempre que contador mudar, pois ele está listado no array de dependências ([contador]).
3. **Função de limpeza:** Nesse exemplo, a função de limpeza não é necessária, mas é útil para situações como remoção de event listeners ou cancelamento de requisições de rede.

**Array de dependências**

O array de dependências controla quando o *useEffect* é disparado:

- **Sem dependências:** O efeito será executado toda vez que o componente for renderizado ou re-renderizado.

```javascript

useEffect(() => {
  console.log('Este efeito será executado em toda renderização');
});

```

- **Array vazio ([]):** O efeito será executado apenas uma vez, na montagem do componente (comportamento semelhante a componentDidMount).

```javascript

useEffect(() => {
  console.log('Este efeito será executado apenas uma vez');
}, []);

```

- *Com dependências:** O efeito será executado sempre que algum dos valores no array de dependências for alterado.

```javascript

useEffect(() => {
  console.log('Este efeito será executado quando "contador" mudar');
}, [contador]);

```

**Função de limpeza (Cleanup)**

A função de limpeza é opcional, mas extremamente útil em situações onde você precisa limpar ou cancelar algo quando o componente é desmontado ou o efeito é reexecutado. Um exemplo comum é limpar assinaturas de eventos ou cancelar timers.

Exemplo com *setInterval*:

```javascript

useEffect(() => {
  const intervalo = setInterval(() => {
    console.log('Executando a cada 1 segundo');
  }, 1000);

  // Função de limpeza para limpar o intervalo ao desmontar o componente
  return () => clearInterval(intervalo);
}, []);

```

**Casos comuns de uso do *useEffect***

1. Busca de dados em APIs:

```javascript

useEffect(() => {
  fetch('https://api.example.com/dados')
    .then((response) => response.json())
    .then((data) => setDados(data));
}, []);

```

2. Adicionando e removendo listeners:

```javascript

useEffect(() => {
  const handleResize = () => {
    console.log('Redimensionado');
  };
  window.addEventListener('resize', handleResize);

  return () => {
    window.removeEventListener('resize', handleResize); // Limpeza
  };
}, []);

```

3. Sincronizando dados com local storage:

```javascript

useEffect(() => {
  const valor = localStorage.getItem('meuValor');
  if (valor) {
    setValor(valor);
  }
}, []);

useEffect(() => {
  localStorage.setItem('meuValor', valor);
}, [valor]);

```

**Boas práticas ao usar *useEffect***

1. **Gerenciar dependências corretamente:** Sempre inclua no array de dependências todas as variáveis que são usadas no corpo do useEffect. Isso previne bugs, como trabalhar com valores desatualizados.

2. **Evite efeitos desnecessários:** Não execute efeitos repetidamente se não houver necessidade. Por exemplo, um useEffect com um array vazio só deve ser usado se o efeito realmente precisa ser executado apenas uma vez (como em buscas iniciais de dados).

3. **Cuidado com dependências complexas:** Para evitar reexecuções desnecessárias, tenha cuidado ao passar objetos ou funções como dependências. Se esses objetos ou funções mudarem constantemente, o efeito será reexecutado mesmo sem necessidade.

---

## O que é a Fetch API?

A Fetch API é uma interface nativa do JavaScript que permite fazer requisições HTTP (como GET, POST, PUT, DELETE) para acessar recursos externos, como APIs e servidores web. Ela substitui o antigo XMLHttpRequest e oferece uma maneira mais simples e moderna de interagir com dados no lado do cliente (front-end).

A Fetch API trabalha de maneira assíncrona, ou seja, você pode solicitar dados a uma API e continuar executando outras tarefas enquanto espera pela resposta. Ela usa Promises, o que facilita o tratamento de sucesso e falha de uma requisição.

**Como Funciona?**

A fetch() retorna uma Promise que será resolvida quando a resposta da requisição estiver disponível. Esse fluxo assíncrono permite que você faça requisições sem travar a interface do usuário, o que é essencial para criar experiências fluidas em aplicativos.

- **Estrutura básica:**

```javascript

fetch('URL-da-API')
  .then(response => response.json()) // Processa a resposta e converte para JSON
  .then(data => console.log(data))   // Manipula os dados retornados
  .catch(error => console.error('Erro:', error)); // Lida com erros

```

**Conceitos Importantes:**

1. URL: O primeiro argumento do fetch() é a URL da API ou recurso que você deseja acessar.

2. Resposta (Response): A resposta inicial que o fetch() retorna contém metadados, como status da requisição e headers, mas o corpo da resposta precisa ser processado (normalmente convertido para JSON, que é o formato mais comum para APIs).

3. Métodos HTTP: Embora o método padrão seja GET, você pode configurar fetch() para usar outros métodos HTTP como POST, PUT, DELETE, etc., dependendo do que você precisa.

```javascript

fetch('https://exemplo.com/api', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ nome: 'João', idade: 25 })
});

```

4. Promises: fetch() retorna uma Promise, que permite que você encadeie .then() para lidar com a resposta assíncrona ou .catch() para lidar com erros, como falhas na rede.

**Exemplo Prático com Fetch API**

Aqui está um exemplo em React de como usar o fetch() para fazer uma requisição GET e exibir dados de uma API:

```javascript

import { useState, useEffect } from 'react';

function App() {
  const [dados, setDados] = useState(null);  // Armazena os dados da API
  const [carregando, setCarregando] = useState(true); // Indica estado de carregamento
  const [erro, setErro] = useState(null);    // Armazena erros, caso ocorram

  useEffect(() => {
    // Faz a requisição HTTP ao montar o componente
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then(response => {
        if (!response.ok) { // Verifica se a resposta foi bem-sucedida
          throw new Error('Erro na requisição');
        }
        return response.json();  // Converte a resposta para JSON
      })
      .then(data => {
        setDados(data);  // Atualiza o estado com os dados recebidos
        setCarregando(false);  // Desativa o carregamento
      })
      .catch(error => {
        setErro(error);  // Armazena o erro
        setCarregando(false);  // Desativa o carregamento mesmo em caso de erro
      });
  }, []);  // O array vazio [] significa que o efeito será executado apenas uma vez, quando o componente for montado

  if (carregando) return <div>Carregando...</div>;
  if (erro) return <div>Erro: {erro.message}</div>;

  return (
    <div>
      <h1>Posts</h1>
      <ul>
        {dados.map(post => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;

```

**Passo a Passo do Exemplo:**

1. useState: Três estados são usados:

- dados para armazenar os dados retornados pela API.
- carregando para controlar se os dados estão sendo buscados.
- erro para armazenar qualquer erro que ocorra.

2. useEffect: Faz a requisição assim que o componente é montado, graças ao array de dependências vazio ([]).

3. fetch:

- Requisição é feita para o endpoint da API https://jsonplaceholder.typicode.com/posts.
- Os dados são convertidos para JSON com response.json() e armazenados no estado dados.
- Caso ocorra um erro, ele é capturado no bloco catch e armazenado no estado erro.

4. Renderização Condicional: Exibe uma mensagem de carregamento, uma mensagem de erro ou os dados da API dependendo do estado atual.

**Vantagens da Fetch API**

- **Simples de usar:** A Fetch API tem uma sintaxe concisa e é fácil de aprender.
- **Baseada em Promises:** Faz com que o código seja mais legível e fácil de manter.
- **Nativa do JavaScript:** Não requer bibliotecas externas.

**Limitações da Fetch API**

- **Faltam algumas funcionalidades:** O fetch() não faz automaticamente a conversão de respostas JSON, e o manuseio de erros é um pouco mais manual.
- **Não aborta requisições facilmente:** Embora seja possível cancelar uma requisição com AbortController, isso requer um pouco mais de configuração.

------

## React Router

O React Router é uma biblioteca popular para o React que permite criar navegação e gerenciar rotas em uma aplicação de página única (SPA - Single Page Application). Em uma SPA, todo o conteúdo está em uma única página HTML, e a navegação é gerenciada no front-end, sem recarregar a página completamente, o que resulta em uma experiência mais fluida para o usuário.

**Conceitos Básicos do React Router**

1. **Roteamento de SPA:** Em vez de fazer requisições para carregar novas páginas do servidor, o React Router altera o conteúdo visível na tela com base na rota da URL, sem recarregar a página. Isso é ideal para aplicações modernas onde a transição entre as páginas deve ser rápida.

2. **Rota (Route):** Define qual componente deve ser renderizado para uma URL específica. Por exemplo, a rota /home pode exibir o componente HomePage, enquanto a rota /about exibe o componente AboutPage.

3. **Navegação (Link):** No React Router, o componente <Link> substitui o <a> do HTML para navegação interna. Ele previne recarregamentos completos de página e usa o histórico de navegação do navegador para fazer a transição entre as rotas.

4. **Switch/Routes:** O componente <Switch> (na versão 5) ou <Routes> (na versão 6) é usado para renderizar apenas a primeira rota que corresponda à URL atual, garantindo que apenas uma rota seja exibida por vez.

**Quando Usar o React Router**

Você deve usar o React Router quando precisa de navegação entre diferentes “páginas” ou seções em uma aplicação React, especialmente se ela é uma SPA. É útil para organizar o conteúdo, melhorar a experiência do usuário e permitir que ele navegue entre diferentes partes da aplicação sem recarregamentos.

**Exemplo Prático**

Vamos supor que você tem uma aplicação com três páginas: Home, About, e Contact. Aqui está uma configuração básica do React Router:

1. Instalação:

```javascript

  npm install react-router-dom

```
2. Configuração do Router:

Crie um arquivo App.js e importe os componentes necessários do React Router:

```javascript

import React from 'react';
import { BrowserRouter as Router, Routes, Route, Link } from 'react-router-dom';
import HomePage from './HomePage';
import AboutPage from './AboutPage';
import ContactPage from './ContactPage';

function App() {
  return (
    <Router>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
        <Link to="/contact">Contact</Link>
      </nav>

      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<AboutPage />} />
        <Route path="/contact" element={<ContactPage />} />
      </Routes>
    </Router>
  );
}

export default App;

```

3. Criando Componentes para Cada Página:

Crie cada uma das páginas (exemplo para HomePage.js):

```javascript

import React from 'react';

function HomePage() {
  return <h1>Home Page</h1>;
}

export default HomePage;

```

Repita esse processo para AboutPage.js e ContactPage.js, alterando o conteúdo conforme necessário.

**Como Funciona**

1. **Router:** O componente <Router> (aqui usando BrowserRouter) envolve toda a aplicação, permitindo o uso de rotas internas.

2. **Link:** Os componentes <Link> gerenciam a navegação interna sem recarregar a página. Por exemplo, ao clicar no link "About", o React Router intercepta a navegação e carrega o componente AboutPage sem recarregar a página.

3. **Routes e Route:** O <Routes> define um conjunto de rotas. O <Route> especifica o caminho da URL (path) e o componente a ser exibido (element) para aquela rota.

**Benefícios do React Router**

- **Experiência de usuário melhorada:** A navegação é mais rápida.
- **URLs amigáveis:** URLs descritivas ajudam na organização e na acessibilidade.
- **Histórico de navegação:** O histórico do navegador é utilizado, permitindo o uso dos botões "voltar" e "avançar".
