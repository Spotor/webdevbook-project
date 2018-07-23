# Angular CLI

O **Angular CLI** é uma ferramenta para inicializar, desenvolver, criar conteúdo e manter software desenvolvido em Angular [@angularclihome]. A principal utilização dessa ferramenta começa na criação de um projeto. Você pode fazer isso manualmente, claro, mas lidar com todas as configurações necessárias para o seu software Angular pode não ser algo fácil, mesmo se você for um desenvolvedor com nível de conhecimento médio a avançado.

---

**cê-éle-í?**

Como parte do vocabulário do Angular, geralmente é interessante pronunciar angular cê-ele-i, isso mesmo, CLI é uma sigla para *Command Line Interface* (no português Interface de Linha de Comando). Assim, usar "cli" não é exclusividade  do Angular -- provavelmente você verá isso em outros projetos.

---

As seções a seguir vão apresentar como instalar e utilizar o Angular CLI para desenvolver software Angular.

## Instalando

O Angular CLI é distribuído como um pacote do **Node.JS**, então você não encontrará um instalador, como acontece com software tradicional. Ao invés disso, você precisa de um ambiente de desenvolvimento com o NodeJS instalado (veja [@sec:apendice-1]).

## Comandos

O Angular CLI disponibiliza uma série de comandos, que são fornecidos como parâmetros para o programa ng. Além disso, cada comando possui diversas opções (ou **flags**). Faça o exercício de se acostumar a essas opções para aumentar a sua produtividade.

Os principais comandos serão apresentados nas seções seguintes.

### help

O comando `help` é muito importante porque apresenta uma documentação completa do Angular CLI, ou seja, todos os comandos e todas as suas opções.

**Exemplo: documentação completa**

```{style=nonumber .sh}
$ ng help
```

Essa linha de comando apresenta todos os comandos e todas as suas opções.

**Exemplo: documentação do comando **`new`**:**

```{style=nonumber .sh}
$ ng help new
```

Essa linha de comando apresenta apenas as opções do comando `new`.

As opções de cada comando são sempre precedidas de `--` (dois traços). Algumas opções aceitam um valor e geralmente possuem um valor padrão.

**Exemplo: comando new com duas opções**

```{style=nonumber .sh}
$ ng new escola-app --skip-install --routing true --minimal true
```

Essa linha de comando fornece três opções para o comando `new`: `--skip-install`, `--routing` (que recebe o valor `true`) e `--minimal` (que recebe o valor `true`).

### new

O comando `new` é utilizado para criar um projeto \(um software Angular\). Exemplo:

```{style=nonumber .sh}
$ ng new escola-app
```

Quando a linha de comando do exemplo for executada será criado um software Angular chamado **escola-app** e estará em um diretório chamado `escola-app`, localizado a partir de onde a linha de comando estiver sendo executada.

A parte mais interessante de criar um projeto Angular com esse comando é que ele cria todos os arquivos necessários para um software bastante simples, mas funcional.

Para cada comando do Angular CLI é possível informar opções. As opções mais usadas do comando `new` são:

* `--skip-install`: faz com que as dependências não sejam instaladas
* `--routing`:  se for seguida de `true`, o comando cria um módulo de rotas (isso será visto em outro capítulo)

### generate

O comando `generate` é utilizado para criar elementos em um projeto existente. Para simplificar, é bom que o Angular CLI seja executado a partir do diretório do projeto a partir de agora. Por meio desse comando é possível criar:

* class
* component
* directive
* enum
* guard
* interface
* module
* pipe
* service

Como acontece com outros comandos, o `generate` também pode ser utilizado por meio do atalho `g`.

**Exemplo: criar component ListaDeDisciplinas**

```{style=nonumber .sh}
$ ng generate component ListaDeDisciplinas
```

Essa linha de comando criará o diretório `./src/app/lista-de-disciplinas` e outros quatro arquivos nesse mesmo local:

* `lista-de-disciplinas.component.css`
* `lista-de-disciplinas.component.html`
* `lista-de-disciplinas.component.spec.ts`
* `lista-de-disciplinas.component.ts`

É importante notar que esses arquivos não estão vazios, mas já contêm código que mantém o software funcional e utilizável. Por isso o Angular CLI considera que as opções (class, component etc.) são como **blueprints** (ou plantas, em português). Outra coisa importante é que o Angular CLI também modificará o arquivo `./src/app/app.module.ts` se necessário (ou outro arquivo que represente um módulo que não seja o **root module** -- mais sobre isso depois).

### serve

O comando `serve` compila o projeto e inicia um servidor web local. Por padrão o servidor web executa no modo `--watch` , que reinicia o comando novamente, de forma incremental, sempre que houver uma alteração em algum arquivo do projeto, e `--live-reload`, que recarrega o projeto no browser (se houver uma janela aberta) sempre que houver uma mudança.

### build

O comando `build` compila o projeto, mas não inicia um servidor web local. Ao invés disso, gera os arquivos resultantes da compilação em um diretório indicado.

Veremos mais sobre esses e outros comando no decorrer do livro.

---

**Espera! Você disse compilação?**

Como já disse, você pode utilizar JavaScript ou TypeScript ao desenvolver projetos Angular. Isso não é bem assim. Na prática, geralmente você encontrará a recomendação (senão uma ordem) de utilizar TypeScript. O problema é que seu Browser não entende TypeScript, por isso é necessário um processo de tradução do código TypeScript para JavaScript. E não é só isso. Há vários recursos utilizados no projeto Angular criado com TypeScript que precisam de ajustes para que funcionem no seu Browser.

Por isso os comandos `serve` e `build` são tão importantes e -- por que não dizer? -- **browser-friendly** =)

---

