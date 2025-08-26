# Introdução

A JavaScript é uma linguagem de programação de alto nível, interpretada, criada originalmente para rodar dentro de navegadores e permitir que páginas da web fossem dinâmicas e interativas.

Para executar um código JavaScript, pode-se criar um **script.js**, e executá-lo em um **index.html**, da seguinte maneira:

```
<meta charset="UTF-8">
<script src="script.js"> </script>
```

> Note que o parâmetro **src** recebe o caminho/nome do script.

Além dessa forma, pode-se apenas declarar uma tag `<script></script>` e um arquivo `.html`, da seguinte maneira:

```
<meta charset="UTF-8">
<script> 
    // código a ser escrito
</script>
```

> Ambas as maneiras serão utilizadas aqui

## Leitura, Escrita e Variáveis

- Usar `alert('mensagem');` vai exibir um pop-up na tela com a mensagem. 
- Usar `console.log('mensagem');` vai exibir a mensagem no terminal do navegador. 
- O `prompt('mensagem');` abre um pop-up com recepção a entrada do usuário, e com uma mensagem.
- Para criar uma variável basta usar `let nome_da_variavel;`, atribuir valor `nome_da_variavel = 10` ou declarar já com valor `let nome_da_variavel = 25;`
- Pode-se atribuir a uma variável com o comando anterior `let variavel = prompt('mensagem');`, mas o conteúdo está em texto.

Exemplo de uso em **script.js**.

```
alert('Bom dia! Boa tarde! Boa noite!');
let nome = prompt('Me diga qual é o seu nome?');
alert('É um prazer te conhecer, ' + nome);
alert('Até nunca mais!!!');
console.log('interação concluida.');
```

## Condicionais

A linguagem oferece suporte a todas as operações aritméticas padrão (`+`, `-`, `*`, `/`, `%`), às operações lógicas (*and*, *or* e *not*, representadas respectivamente por `&&`, `||` e `!`) e também às operações de comparação, como igualdade (`==`), igualdade estrita (`===`), diferença (`!=`), diferença estrita (`!==`), menor ou igual (`<=`), maior ou igual (`>=`), menor (`<`) e maior (`>`).

Para definir fluxos de execução/decisão, deve-se usar as estruturas condicionais `if/else` ou `switch/case`.

```
let num = prompt('Digite um número:');

if(num > 0)
{
    alert(`${num} é um número positivo`);
}
else if(num < 0)
{
    alert(`${num} é um número negativo`);
}
else
{
    alert(`${num} é nulo`);
}
```

> Se **num** é maior que 0, então **num** é positivo. Para primeira **não** verdadeira, e **num** é menor que 0, então **num** é negativo. Senão, **num** é igual a 0 (nulo).

```
let cor = "azul";

switch (cor) 
{
  case "vermelho":
    console.log("A cor é vermelho.");
    break;

  case "azul":
    console.log("A cor é azul.");
    break;

  case "verde":
    console.log("A cor é verde.");
    break;

  default:
    console.log("Cor não reconhecida.");
}
```

> Quando **cor** não é vermelho, azul e nem verde, então não esta **cor** não é conhecida.

> O operador ternário (`condicao ? se_verdadeira : se_falsa;`) é uma maneira de construir uma condicional `if/else`, mas de maneira mais simple. 

## Loops

Loops servem para expressar iterações, ou seja, blocos de execução repetida. Há os comandos `while`, `do/while` e `for`, onde as duas primeiras tem condição de parada **lógica**, e a útima por **contador**. Exemplo de implementação abaixo.

```
let i = 0;
while(i < 5)
{
    i++;
    \\ bloco de instruções
}
```
> '**Enquanto i for menor que 5, então i é incrementado em 1 e executa "bloco de instruções"**'.
```
let j = 0;
do
{
    j = j + 2;
    \\ bloco de instruções
}
while(j != 12);
```
> '**Incrementa j em 2 e faça "bloco de instruções", enquanto j for diferente de 12**'.
```
for(let k = 0; k < 23; k++)
{
    \\ bloco de instruções
}
```
> '**Para k começando em 0, enquanto k for menor que 23 faça "bloco de instruções", e a cada repetição aumente k em 1'**'.

> O comando `break;` quebra/interrompe abruptamente o loop.

> O comando `continue;` força a próxima iteração.

## Biblioteca Math

A biblioteca **Math** do JavaScript fornece um conjunto de funções e constantes matemáticas úteis, permitindo realizar cálculos de forma prática. Entre estas funções, tem-se funções de arredondamento (``Math.round``, ``Math.floor``, ``Math.ceil``), de cálculos de potência e raiz (``Math.pow``, ``Math.sqrt``), de obter valores absolutos (``Math.abs``). Além destas, também disponibiliza funções trigonométricas (``Math.sin``, ``Math.cos``, ``Math.tan``), logarítmicas (``Math.log``, ``Math.exp``), constantes matemáticas (``Math.PI``, ``Math.E``). Outra função bastante usada é ``Math.random``, que gera números pseudoaleatórios entre 0 e 1, incluindo 0, mas não o 1.

> Esta biblioteca foi imporatante para um jogo da adivinhação.

> O método ``toFixed`` e a função``parseInt`` servem para limitar a quantidade de casas decimais de um número e para converter um texto para número, respectivamente.

## Funções

 **Function** é um bloco de código reutilizável que executa uma tarefa específica ou retorna um valor quando chamado. As funções permitem organizar o programa em módulos, facilitando a leitura, a manutenção e o reaproveitamento do código. 
 
 Funções podem receber parâmetros (valores de entrada) e retornar um resultado com a instrução ``return``. Para defini-las, utiliza-se o bloco ``function nome(){...}``. 
 
 ```
function geraNumeroAleatorio(inicio,fim)
{
	if(inicio >= fim)
		return 0;
	let res = Math.round((Math.random() * (fim - inicio) + inicio));
	return res;
}
 ```

> Para chamá-la, basta atribuir a uma variável a chamada da função (ex.: `let intervalo_1_a_10 = geraNumeroAleatorio(1,10);`).

## Sequências

**Arrays** são estruturas de dados que armazenam múltiplos valores em uma única variável, organizados por índices numéricos que começam em 0. Podem conter elementos de qualquer tipo (números, strings, objetos, funções etc.) e até misturar diferentes tipos dentro do mesmo array. 

Arrays oferecem um conjunto amplo de propriedades e métodos úteis, como ``length`` (quantidade de elementos), ``push`` e ``pop`` (adicionar ou remover no final), ``shift`` e ``unshift`` (remover ou adicionar no início), além de funções de iteração como ``forEach``, ``map``, ``filter`` e ``reduce``. Abaixo um exemplo de uso:

```

function print(msg)
{
    document.write(msg + "<br>");
}

let frutas = ["maçã", "banana", "uva"];

print(frutas.length); 

frutas.push("laranja");
print(frutas);

frutas.pop();
print(frutas); 

frutas.unshift("manga");
print(frutas); 

frutas.shift();
print(frutas); 

frutas.forEach((fruta, i) => {
	print(`item ${i} do array: ${fruta}`);
});

let frutasMaiusculas = frutas.map(f => f.toUpperCase());
print(frutasMaiusculas);

let frutasComA = frutas.filter(f => f.includes("a"));
print(frutasComA); 
```

> Arrays  são fundamentais para armazenar e manipular coleções de dados de forma dinâmica em aplicações JavaScript.

## Interagir no HTML

Abaixo algumas tags da linguagem HTML para utilizar essa interação entres JavaScript e HTML.

- `<br>` pula linha na página.
- `<h1> texto </h1>` põe o texto em caixa de título.
- `<a href="https://github.com/Serumaninhow"> meu git </a>` faz um link clicável e já direcionado.
- `<p>texto</p>` põe o texto em forma de parágrafo na página.
- `<big>texto</big>` aumenta fonte do texto na página.
- `<input id="entrada"/>` cria uma caixa de texto com id = "entrada".
- `<button id="botao"></button>` cria botão de id="botao".

Abaixo um exemplo utilizando métodos para referenciar os objetos `input` e `button` a partir de seus **id's** (`getElementById("id")`), resgatar o valor de entrada (`value`), focar a caixa de texto (`focus()`) e fazer uma ação ao clicar do botão (`onclick`).

```
<meta charset="UTF-8">

<input id="entrada"/>
<button id="botao">botão</button>

<script>

    var input = document.getElementById("entrada");
    input.focus();

    function imprimeDigitado()
    {
		if(input.value != "")
		{
			alert(input.value);
			input.value = "";	
		}
        input.focus();
    }

    var button = document.getElementById("botao");

    button.onclick = imprimeDigitado;

</script>
```

> O referente exemplo abre um pop-up quando digita-se algum texto na caixa e em seguida clica-se no botão.

## Alguns conceitos importantes

O HTML (HyperText Markup Language) é a linguagem de marcação utilizada para estruturar o conteúdo de uma página web. Essa linguagem usa tags para definir a hierarquia dos elementos de uma página. Originado em 1991 por Tim Berners-Lee, o HTML é como o esqueleto de uma página web: trabalha organizando o conteúdo, como títulos, parágrafos, imagens e links, para que tudo fique bem arrumado e no lugar certo.

O CSS (Cascading Style Sheets), criado em 1995, é destacado como uma linguagem de estilos. Ele separa a apresentação da estrutura: é responsável pela apresentação e estilização dos elementos, pois permite controlar cores, fontes, layouts e outros aspectos visuais. É como vestir a estrutura HTML com roupas elegantes para que a página pareça exatamente como você deseja.

O JavaScript, por sua vez, é a única linguagem de programação das três. É responsável por adicionar interatividade e dinamismo às páginas. Possibilita a criação de funcionalidades como animações, validações de formulários e atualizações de conteúdo em tempo real.

> O papel de cada tecnologia dessas na construção de aplicações web, de forma bem resumida, é: o HTML estrutura o conteúdo, o CSS define o estilo e o layout, e o JavaScript adiciona funcionalidades dinâmicas.

## Considerações Finais

JavaScript é uma linguagem essencial para o desenvolvimento web, pois possibilita a criação de páginas dinâmicas, interativas e responsivas. Os primeiros passos apresentados nesse material já constroem a base necessária para resolver problemas e construir aplicações que interajam diretamente com o usuário. Assim, o domínio desses fundamentos abre caminho para o aprofundamento em recursos mais avançados, como **frameworks**, **bibliotecas** modernas e **API's**, tornando este aprendizado uma introdução para quem queira atuar no desenvolvimento de software web.

