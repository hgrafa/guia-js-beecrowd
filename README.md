<h1 align='center'>
   BEECROWD - GUIA DE SOLUÇÕES COM JAVASCRIPT
</h1>

- Guia de como resolver problemas do Beecrowd com JavaScript.

# 📒 Sumário

1. [Guia](#-ta-com-duvida-em-como-enviar-respostas-com-js)
2. [Como Contribuir pro repositório](#-como-contribuir)

# 🤔 Ta com duvida em como enviar respostas com Javascript?

<p> 
Muitos programadores sentem dificuldades em solucionar os problemas do beecrowd com JavaScript por não entender como funciona a entrada de dados. Relaxa! Eu vou te explicar:

Primeiramente, crie um arquivo chamado 'stdin' em sua pasta. Iremos usar esse arquivo para ler os valores do nosso problema!

<img src= 'assets/img1.png' >

Agora, vamos resolver o problema [1001](https://www.beecrowd.com.br/judge/pt/problems/view/1001) do Beecrowd. Para isso, temos que iniciar declarando o nosso input:

```
var input = require('fs').readFileSync('stdin', 'utf8')
```

Para recebermos os valores da entrada, precisamos fazer uma requisição do módulo conhecido como 'fs'. Este módulo fornece operações de I/O (Input/Output ou E/S, Entrada/Saída).

Não iremos entrar muito em detalhes de como o 'fs' funciona, pois iremos usar apenas a função [readFileSync](https://www.geeksforgeeks.org/node-js-fs-readfilesync-method/) do 'fs', essa função permite a leitura de forma síncrona do arquivo que iremos passar como parâmetro da função, junto com seu tipo de arquivo 'utf8'.

Ok, nosso input está pronto! Vamos testar? Entre no arquivo stdin e digite 10 e 9 um em cada linha, em seguida digite `console.log(input)` no código.

<img src= 'assets/img2.png'>

Perceba que foi impresso 10 e 9, conforme digitados no arquivo stdin! Pois o nosso input está lendo os valores digitados naquele arquivo.

Vamos agora para o próximo passo!

```js
var valoresRecebidos = input.split('\n')
```

Digite isso no seu código. Perceba que declaramos uma variável chamada `valoresRecebidos`, essa variável irá receber os valores do input e armazena-los. Mas, por que usar o método `.split`? A resposta é simples, o nosso input esta retornando uma string, então o método split irá criar uma lista ordenada de substrings de acordo com o nosso divisor, que no caso foi o "\n", pois precisamos quebrar linha na hora de receber os valores conforme o beecrowd pede.

Vamos imprimir a variável _valoresRecebidos_ para acompanhar o processo:

<img src= 'assets/img3.png'>

Perceba que foi retornada uma lista com os valores de acordo como nos separamos eles! No caso usando uma quebra de linhas igual o problema pede.

Agora ficou fácil! Só precisamos armazenar os valores 10 e 9 em suas respectivas variáveis, no caso _A_ e _B_.

```js
var A = parseInt(valor.shift())
var B = parseInt(valor.shift())
```

Ok... vamos entender o que foi feito! O método _[shift](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)_ em JavaScript remove o primeiro elemento de um array e retorna esse elemento. Ou seja, estamos pegando o primeiro elemento do array `valoresRecebidos` e jogando na variável `A`, em seguida pegamos o segundo elemento e jogamos na variável `B`. Mas não acabou por aí, perceba que temos que receber valores inteiros da entrada/inputs, ou seja, temos que converter o elemento que estamos recebendo do array para valores _inteiros_, para isso basta usarmos a função [`parseInt()`](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/parseInt), essa função retorna um valor inteiro do elemento que estamos passando!

Pronto! Agora é só a gente criar a variável X e fazer a soma entre A e B!

```js
var X = A + B
```

Por fim, nosso código ficará assim:

```js
var input = require('fs').readFileSync('stdin', 'utf8')

var valoresRecebidos = input.split('\n')

var A = parseInt(valoresRecebidos.shift())
var B = parseInt(valoresRecebidos.shift())

var X = A + B

console.log('X = ' + X)
```

Vamos testa-lo para ver se ta funcionando conforme o beecrowd deseja!

<img src= 'assets/img4.png'>

Aeee! Bingo! Você conseguiu resolver o problema 1001 do beecrowd! Não pera... Ainda falta um maldito detalhe 😜. Sabe a nosso input que ta lendo o arquivo '`stdin`'? Esse arquivo tem o mesmo nome do arquivo que compila e verifica as entradas no própio beecrowd! Ou seja, com esse comando vamos estar acessando as pastas do beecrowd e receber os valores da entrada. Só que o diretório do arquivo stdin do beecrowd é diferente do nosso! Se enviarmos assim, nossa solução irá dar `Runtime error`. Para resolver esse problema, devemos apenas adicionar o "/dev/stdin" no nosso parâmetro da função 😀.

Veja:

```js
var input = require('fs').readFileSync('/dev/stdin', 'utf8')
```

Agora sim! O resultado final:

```js
var input = require('fs').readFileSync('/dev/stdin', 'utf8')

var valoresRecebidos = input.split('\n')

var A = parseInt(valoresRecebidos.shift())
var B = parseInt(valoresRecebidos.shift())

var X = A + B

console.log('X = ' + X)
```

Parabéns!! Você conseguiu resolver o problema 1001 do beecrowd com JavaScript, a linguagem mais bonita da internet (brincadeira... ou não...).

Se esse conteúdo foi útil para você, por favor clique na star do respositório, pois ficarei muito feliz em saber que de alguma maneira fiz algo útil para alguém da nossa comunidade. Me adiciona lá no beecrowd pra gente ver nossas conquistas! Basta clicar aqui: [GabrielDuete-beecrowd](https://www.beecrowd.com.br/judge/pt/profile/412152).

Muito obrigado por ter lido até aqui e ter aprendido, você é incrível mesmo 💜. Nunca desista dos estudos e continue focado mesmo com tantas dificuldades e coisas pra estudar, eu sei que você consegue!

<cite> 
<blockquote>"COM TRABALHO DURO UM FRACASSADO CONSEGUE ATÉ MESMO SUPERAR UM GÊNIO." - Rock Lee
</blockquote>
</cite>

</p>

# 📌 Como contribuir

## Quer contribuir?

<p> 

### Primeiro organize o setup:

1. Realize um Fork do projeto
2. Vá até o repositório do fork no seu github e na parte code copie o link para clonar
3. Abra o terminal, escolha uma pasta de sua preferência e faça um clone git clone cole o link que você copiou

#### Contribuindo pro guia:

1. Faça suas alterações no README.md
2. Crie um branch para subir suas alterações a partir da main `(git checkout -B <sua-branch>)`
3. Depois faça `git add .`
4. Realize o Commit tipo: `git commit -m 'feat: melhorando algo :)'`
5. Realize o Push no Branch `git push origin <sua-branch>`
6. Abra um Pull Request

</p>
