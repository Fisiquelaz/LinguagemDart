# Linguagem Dart


Repositório para o seminário da matéria Programação Orientada a Serviços

Alunos:
1. Anderson Pereira - AndersonPT07 - 20141011110379
2. Danilo Miranda - Fisiquelaz - 20141011110360
3. Vinicus Malafaya - malafaya9 - 20141011110280

## RESUMO

**Propósito da linguagem:**
  - Desenvolver servidores e aplicações web e mobile
  - Fornecer uma base sólida de bibliotecas e ferramentas
  - Facilitar as tarefas comuns de programação
  - Ser a solução pragmática e estável para aplicativos reais

**Paradigma da linguagem:**
  - Multiparadigma - funcional e procedural

**Data de criação:**
  - Foi lançada na GOTO Conference 2011, que aconteceu de 10 a 11 de outubro de 2011 em Aarhus, na Dinamarca.

**Principal mantenedor:**
  - Google

## Instalação e uso:

1. Acesse este [link](https://www.dartlang.org/install/archive "Instalação") e baixe o arquivo de acordo com seu SO ou utilize o [DartPad](https://dartpad.dartlang.org/) para desenvolver no chrome
2. Baixe o arquivo ZIP de acordo com seu SO e descompacte
3. Abra o prompt de comandos e se direcione até o diretório em que o Dart foi instalado
4. Siga para a pasta "diretorio"/bin, crie um arquivo novoarquivo.dart e insira o código
5. Para executar o arquivo, insira o comando "dart novoarquivo.dart"
6. Para compilar para JavaScript, insira "dart2js --out=arquivo.js novoarquivo.dart"

## Sintaxe Básica

#### Variáveis
Declarações de variáveis:

~~~~
var name;
name = 'Voyager I'
var year = 1977;
var antennaDiameter = 3.7;
var flybyObjects = ['Jupiter', 'Saturn', 'Uranus', 'Neptune'];
var image = {
  'tags': ['saturn'],
  'url': '//path/to/saturn.jpg'
};
~~~~
Variáveis tambem podem ter seu tipo(string, int, etc) definido antes, como:

~~~~
string name = 'Voyager I';
int year = 1977;
double antennaDiameter = 3.7;
~~~~



#### Operadores aritméticos, relacionais e lógicos
Os seguintes operadores são suportados:

~~~~
+ - / * // Soma, subtração, divisão, multiplicação
-expressao // Inverte o sinal da expressão dada(positivo vira negativo, etc)
~/ // Divisão, como retorno sempre em inteiro
% // Retorna o resto da divisão entre dois valores

== != > < >= <= // Igualdade, desigualdade, maior que, menor que, maior ou igual, menor ou igual

!expressao // Inverte o valor da expressão dada(true vira false, etc)
&& // Operador lógico para E
|| // Operador lógico para OU
~~~~
Exemplos:

~~~~
if(a + b == c && b - a != c) {...}
if(a / c > b || b * a <= c) {...}
if(a ~/ b < c && b % a >= c) {...}
~~~~



#### Estruturas de controle condicional
As seguintes formas de controle condicional são suportadas:

~~~~
if(condição){...}
else {...}
//Testa a condição dentro do if, Caso verdadeiro, executa seu código. Caso falso, executa o código no else(caso presente)

condição ? expr1 : expr2 // Testa a condição apresentada. Caso verdadeiro, retorna a expr1. Caso falso, retorna a expr2
~~~~
Exemplos:

~~~~
if(a != null) {print(a);}
else {print("Insira um valor");}

a != null ? print(a); : print("Insira um valor");
~~~~



#### Estruturas de repetição
As seguintes estruturas de repetição são suportadas:

~~~~
for(inicializador; condição; iterador){...} // O inicializador configura as condições iniciais. O laço é iniciado e só prossegue enquanto a condição for verdadeira, assim que a mesma for falsa, o laço é interrompido. Ao fim de cada iteração, o iterador é acionado

while(condição){...} // Executa um bloco de código enquanto a condição for verdadeira

do{...}
while(condição)
//Executa um bloco de código uma vez, depois verifica a condição. Caso verdadeira, prossegue repetindo o código. Caso falsa, interrompe o laço
~~~~
