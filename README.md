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

final int constante; //definindo uma constante
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
Exemplos:

~~~~
for(int i = 0; i<5; i++){print(i);}

var i=0;
while(i<5)
{
  print(i);
  i++;
}

var i = 0;
do
{
  print(i);
  i++;
}
while(i<5)
~~~~

#### Vetores, matrizes e strings
Declarando vetores, matrizes e strings

~~~~
var vetor = [1, 2, 3] // As posições são guardadas como [0], [1], [2]. Tambem funciona como lista

List<List<int>> matriz = new List<List<int>>(); // Para cirar uma matriz, cria-se uma lista de listas

String texto = 'texto' // Pode ter o valor atribuido com aspas simples ou duplas
~~~~
Exemplos:

~~~~
var vetor = []
for(num i = 0; i < 5; i++)
{
  vetor.push(i);
}
print(vetor);

List<List<int>> matriz = new List<List<int>>();
  for (var i = 0; i < 10; i++) {
    List<int> lista = new List<int>();
    for (var j = 0; j < 10; j++) {
      lista.add(j);
    }
    matriz.add(lista);
  }
print(matriz);

String s1 = 'Essa é ';
String s2 = s1 + 'a forma de concatenar uma string.\n';
String s3 = "E essa é ";
String s4 = "$s3 a forma de interpolar";
print(s2+s4);
~~~~

#### Funções
Declarando funções

~~~~
void main() {
  Funcao() {...}
}
~~~~

Se tiver uma função que invoca um método com os mesmos argumentos que são passados para ele, não é necessário quebrar manualmente a chamada em um lambda.

Errado
~~~~
void main() {
  var localFunction = () {
    ...
  };
}
~~~~

certo
~~~~
void main() {
  localFunction() {
    ...
  }
}
~~~~

## Sintaxe OO

#### Classes

~~~~
//Classse
class Spacecraft {
  String name; //Atributos com visibilidade publica 
  DateTime launchDate;
  int launchYear;
  String _atributoPrivado; //Atributo com visibilidade privada 

  // Construtor, incluindo syntactic sugar para atribuição aos membros.
  Spacecraft(this.name, this.launchDate) {
    // Finja que o seguinte é algo que você realmente deseja executar em 
    // um construtor. 
    launchYear = launchDate?.year;
  }

  // Construtor nomeado que encaminha para o padrão.
  Spacecraft.unlaunched(String name) : this(name, null);

  //Método
  void describe(String description){  //Sobrecarga no métoro description
    print(description); 
  }
  //Para mudar a visibilidade de um método basta apenas colocar um "_" underline
  void describe() {
    print('Spacecraft: $name');
    if (launchDate != null) {
      int years = new DateTime.now().difference(launchDate).inDays ~/ 365;
      print('Launched: $launchYear ($years years ago)');
    } else {
      print('Unlaunched');
    }
  }
}
~~~~
#### Herança
~~~~
class Orbiter extends Spacecraft {
  num altitude;
  Orbiter(String name, DateTime launchDate, this.altitude)
      : super(name, launchDate);
}
~~~~

#### Sintaxe básica de exceções:

~~~~
if (astronauts == 0) {
  throw new StateError('No astronauts.');
}
~~~~
Exceções podem ser detectadas, mesmo em código assíncrono.
~~~~
try {
  for (var object in flybyObjects) {
    var description = await new File('$object.txt').readAsString();
    print(description);
  }
} on IOException catch (e) {
  print('Could not describe object: $e');
} finally {
  flybyObjects.clear();
}
~~~~
Criando nova e exceção personalizada
~~~~
class CustomException implements Exception {
  String cause;
  CustomException(this.cause);
}

void main() {
  try {
    throwException();
  } on CustomException {
    print("custom exception is been obtained");
  }
}

throwException() {
  throw new CustomException('This is my first custom exception');
}
~~~~

## Sintaxe básica do paradigma da linguagem 
~~~~
HTML
<!DOCTYPE html>

<!--
  Copyright (c) 2012, the Dart project authors.  Please see the AUTHORS file
  for details. All rights reserved. Use of this source code is governed by a
  BSD-style license that can be found in the COPYING file.
-->

<html>
  <head>
    <meta charset="utf-8">
    <title>A Simple ToDo List Using HTML5 IndexedDB</title>
    <link rel="stylesheet" href="todo.css">
  </head>
  <body>
    <input type="text" id="todo" name="todo"
        placeholder="What do you need to do?">
    <input type="submit" id="submit" value="Add Todo Item">
    <ul id="todo-items"></ul>
    <script type="application/dart" src="todo.dart"></script>
    <script src="packages/browser/dart.js"></script>
  </body>
</html>
~~~~
CSS
~~~~
/*
  Copyright (c) 2012, the Dart project authors.  Please see the AUTHORS file
  for details. All rights reserved. Use of this source code is governed by a
  BSD-style license that can be found in the COPYING file.
*/

body {
  color: #222;
  font: 14px Arial;
}

a {
  color: #3D5C9D;
  cursor: pointer;
  text-decoration: none;
}

li a {
  margin-left: 8px;
}

#todo {
  width: 200px;
}
~~~~
DART
~~~~
// Copyright (c) 2012, the Dart project authors.  Please see the AUTHORS file
// for details. All rights reserved. Use of this source code is governed by a
// BSD-style license that can be found in the COPYING file.

// This is a port of "A Simple ToDo List Using HTML5 IndexedDB" to Dart.
// See: http://www.html5rocks.com/en/tutorials/indexeddb/todo/

import 'dart:html';
import 'dart:indexed_db' as idb;
import 'dart:async';

class TodoList {
  static final String _TODOS_DB = "todo";
  static final String _TODOS_STORE = "todos";

  idb.Database _db;
  int _version = 2;
  InputElement _input;
  Element _todoItems;

  TodoList() {
    _todoItems = querySelector('#todo-items');
    _input = querySelector('#todo');
    querySelector('input#submit').onClick.listen((e) => _onAddTodo());
  }

  Future open() {
    return window.indexedDB.open(_TODOS_DB, version: _version,
        onUpgradeNeeded: _onUpgradeNeeded)
      .then(_onDbOpened)
      .catchError(_onError);
  }

  void _onError(e) {
    // Get the user's attention for the sake of this tutorial. (Of course we
    // would *never* use window.alert() in real life.)
    window.alert('Oh no! Something went wrong. See the console for details.');
    window.console.log('An error occurred: {$e}');
  }

  void _onDbOpened(idb.Database db) {
    _db = db;
    _getAllTodoItems();
  }

  void _onUpgradeNeeded(idb.VersionChangeEvent e) {
    idb.Database db = (e.target as idb.OpenDBRequest).result;
    if (!db.objectStoreNames.contains(_TODOS_STORE)) {
      db.createObjectStore(_TODOS_STORE, keyPath: 'timeStamp');
    }
  }

  void _onAddTodo() {
    var value = _input.value.trim();
    if (value.length > 0) {
      _addTodo(value);
    }
    _input.value = '';
  }

  Future _addTodo(String text) {
    var trans = _db.transaction(_TODOS_STORE, 'readwrite');
    var store = trans.objectStore(_TODOS_STORE);
    return store.put({
      'text': text,
      'timeStamp': new DateTime.now().millisecondsSinceEpoch.toString()
    }).then((_) => _getAllTodoItems())
    .catchError((e) => _onError);
  }

  void _deleteTodo(String id) {
    var trans = _db.transaction(_TODOS_STORE, 'readwrite');
    var store =  trans.objectStore(_TODOS_STORE);
    var request = store.delete(id);
    request.then((e) => _getAllTodoItems(), onError: _onError);
  }

  void _getAllTodoItems() {
    _todoItems.nodes.clear();

    var trans = _db.transaction(_TODOS_STORE, 'readwrite');
    var store = trans.objectStore(_TODOS_STORE);

    // Get everything in the store.
    var request = store.openCursor(autoAdvance:true).listen((cursor) {
      _renderTodo(cursor.value);
    }, onError: _onError);
  }

  void _renderTodo(Map todoItem) {
    var textDisplay = new Element.tag('span');
    textDisplay.text = todoItem['text'];

    var deleteControl = new Element.tag('a');
    deleteControl.text = '[Delete]';
    deleteControl.onClick.listen((e) => _deleteTodo(todoItem['timeStamp']));

    var item = new Element.tag('li');
    item.nodes.add(textDisplay);
    item.nodes.add(deleteControl);
    _todoItems.nodes.add(item);
  }
}

void main() {
  new TodoList().open();
}
~~~~
