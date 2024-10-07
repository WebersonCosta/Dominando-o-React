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
