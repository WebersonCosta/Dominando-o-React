# Dominando-o-React
Aqui deixarei minhas anotações do estudo da biblioteca React

---

# O que é o React?

O React é uma biblioteca JavaScript desenvolvida pelo Facebook para construir interfaces de usuário, especialmente em aplicações web. Ele permite criar componentes reutilizáveis, o que facilita o desenvolvimento e a manutenção de grandes aplicações. O React utiliza uma abordagem declarativa, o que significa que você descreve como a interface deve se parecer em diferentes estados, e ele cuida de atualizar a DOM de forma eficiente.

---

## npm

O **npm (Node Package Manager)** é um gerenciador de pacotes para o ambiente *Node.js*. Ele permite que você instale, atualize e gerencie bibliotecas e dependências de *JavaScript* em seus projetos. O npm é uma ferramenta essencial para desenvolvedores que trabalham com *JavaScript*, pois facilita a inclusão de pacotes de código já prontos, como o *React* e suas dependências.

#### Aqui estão algumas funcionalidades principais do npm:

- **Instalação de Pacotes:** Você pode instalar pacotes de forma simples, usando o comando npm install nome-do-pacote. Isso adiciona a biblioteca ao seu projeto e a lista de dependências no arquivo package.json.

- **Gerenciamento de Dependências:** O package.json é um arquivo que contém informações sobre seu projeto, incluindo as dependências que ele usa. O npm lê esse arquivo para instalar as versões corretas dos pacotes.

- **Scripts:** O npm permite que você defina scripts personalizados no package.json, que podem ser executados com comandos como npm run nome-do-script. Isso é útil para automação de tarefas, como iniciar um servidor de desenvolvimento ou executar testes.

- **Publicação de Pacotes:** Você também pode criar e publicar seus próprios pacotes no repositório npm, tornando-os disponíveis para a comunidade.

Ao iniciar um projeto com React, você normalmente usará o npm para instalar o React e suas bibliotecas associadas.

---

## JSX

**JSX** é uma extensão de sintaxe para JavaScript que permite escrever elementos HTML dentro do JavaScript. Ele é frequentemente usado em aplicações React para descrever como a interface de usuário deve parecer.

#### Aqui estão alguns pontos chave sobre JSX:

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

## estado (*state*)

Em React, "estado" refere-se a dados que podem mudar ao longo do tempo. Quando o estado de um componente muda, o React re-renderiza o componente para refletir essas mudanças.

## Previous states

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

## useState

#### Como utilizar adequadamente o *useState* em React

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

#### Atualização do estado

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

#### Estado inicial dinâmico

Você pode usar uma função como argumento de useState para calcular o valor inicial apenas na primeira renderização. Isso é útil para cálculos mais complexos que não precisam ser reexecutados em cada renderização.

**Exemplo:**

```javascript

const [contador, setContador] = useState(() => calcularValorInicial());

```

Aqui, calcularValorInicial() só será chamado na primeira vez que o componente for montado.

#### Boas práticas ao usar *useState*

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

## useEffect

#### Como utilizar adequadamente o *useEffect* em React

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

#### Array de dependências

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

#### Função de limpeza (Cleanup)

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

#### Casos comuns de uso do *useEffect*

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

#### Boas práticas ao usar *useEffect*

1. **Gerenciar dependências corretamente:** Sempre inclua no array de dependências todas as variáveis que são usadas no corpo do useEffect. Isso previne bugs, como trabalhar com valores desatualizados.

2. **Evite efeitos desnecessários:** Não execute efeitos repetidamente se não houver necessidade. Por exemplo, um useEffect com um array vazio só deve ser usado se o efeito realmente precisa ser executado apenas uma vez (como em buscas iniciais de dados).

3. **Cuidado com dependências complexas:** Para evitar reexecuções desnecessárias, tenha cuidado ao passar objetos ou funções como dependências. Se esses objetos ou funções mudarem constantemente, o efeito será reexecutado mesmo sem necessidade.

---

O que é a Fetch API?
A Fetch API é uma interface nativa do JavaScript que permite fazer requisições HTTP (como GET, POST, PUT, DELETE) para acessar recursos externos, como APIs e servidores web. Ela substitui o antigo XMLHttpRequest e oferece uma maneira mais simples e moderna de interagir com dados no lado do cliente (front-end).

A Fetch API trabalha de maneira assíncrona, ou seja, você pode solicitar dados a uma API e continuar executando outras tarefas enquanto espera pela resposta. Ela usa Promises, o que facilita o tratamento de sucesso e falha de uma requisição.

Como Funciona?
A fetch() retorna uma Promise que será resolvida quando a resposta da requisição estiver disponível. Esse fluxo assíncrono permite que você faça requisições sem travar a interface do usuário, o que é essencial para criar experiências fluidas em aplicativos.

Estrutura básica:
javascript
Copiar código
fetch('URL-da-API')
  .then(response => response.json()) // Processa a resposta e converte para JSON
  .then(data => console.log(data))   // Manipula os dados retornados
  .catch(error => console.error('Erro:', error)); // Lida com erros
Conceitos Importantes:
URL: O primeiro argumento do fetch() é a URL da API ou recurso que você deseja acessar.

Resposta (Response): A resposta inicial que o fetch() retorna contém metadados, como status da requisição e headers, mas o corpo da resposta precisa ser processado (normalmente convertido para JSON, que é o formato mais comum para APIs).

Métodos HTTP: Embora o método padrão seja GET, você pode configurar fetch() para usar outros métodos HTTP como POST, PUT, DELETE, etc., dependendo do que você precisa.

javascript
Copiar código
fetch('https://exemplo.com/api', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ nome: 'João', idade: 25 })
});
Promises: fetch() retorna uma Promise, que permite que você encadeie .then() para lidar com a resposta assíncrona ou .catch() para lidar com erros, como falhas na rede.

Exemplo Prático com Fetch API
Aqui está um exemplo em React de como usar o fetch() para fazer uma requisição GET e exibir dados de uma API:

javascript
Copiar código
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
Passo a Passo do Exemplo:
useState: Três estados são usados:

dados para armazenar os dados retornados pela API.
carregando para controlar se os dados estão sendo buscados.
erro para armazenar qualquer erro que ocorra.
useEffect: Faz a requisição assim que o componente é montado, graças ao array de dependências vazio ([]).

fetch:

Requisição é feita para o endpoint da API https://jsonplaceholder.typicode.com/posts.
Os dados são convertidos para JSON com response.json() e armazenados no estado dados.
Caso ocorra um erro, ele é capturado no bloco catch e armazenado no estado erro.
Renderização Condicional: Exibe uma mensagem de carregamento, uma mensagem de erro ou os dados da API dependendo do estado atual.

Vantagens da Fetch API
Simples de usar: A Fetch API tem uma sintaxe concisa e é fácil de aprender.
Baseada em Promises: Faz com que o código seja mais legível e fácil de manter.
Nativa do JavaScript: Não requer bibliotecas externas.
Limitações da Fetch API
Faltam algumas funcionalidades: O fetch() não faz automaticamente a conversão de respostas JSON, e o manuseio de erros é um pouco mais manual.
Não aborta requisições facilmente: Embora seja possível cancelar uma requisição com AbortController, isso requer um pouco mais de configuração.
Próximos Passos
Depois de entender o básico da Fetch API, você pode:

Explorar requisições POST, PUT e DELETE.
Lidar com autenticação (tokens, headers, etc.).
Experimentar a biblioteca Axios, que oferece mais funcionalidades e um manuseio mais fácil de erros.
