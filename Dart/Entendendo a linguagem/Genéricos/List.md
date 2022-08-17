# Formas de declarar uma List:

^9b0873

```dart
  //Lista normal, porém não a melhor alternativa
  List<int> listNumeros = [1, 2, 3];

  //Forma ideal
  var listNumeros2 = [1, 2, 3];

  //Lista sem dados, melhor forma é inferir o tipo
  List<int> listSemdados = [];

  //O dart reclama mas se nao inferirmos o tipo, ela vem como dynamic
  List listSemDados2 = []; 

  //entao a melhor forma é:
  List listSemDados3 = <int>[];
```
Lists que aceitam nulos:
```dart
  //Nao aceita nulos
  var nomes = <String>[];

  //aceita null
  List<String>? nomesAceitaNull = null;

  //aceita null internos
  List<String?> listAceitaNullinternos = [null];
  var listAceitaNullinternos2 = <String?>[null];

  //aceita null internos e externos
  List<String?>? listAceitaNullinternosExterno = null;
```

# Acessando elementos da List: 

^fbfb99

##### [ ]
Acessando elementos pelo índice
```dart
List[indice]
```

##### .last
Acessa o útimo elemento da List
##### .first
Acessa o primeiro elemento da List
# Adicionando elementos na List:

^ee4e08

##### .add(element )
```dart
  var numeros = [1, 2, 3, 4, 5];
  numeros.add(6);
```
>numeros=[1,2,3,4,5,6]
##### .insert(index,element)
```dart
void main() {
  var numeros = [1, 2, 3];
  numeros.insert(0, 0);
  print(numeros);
}
```
>[0, 1, 2, 3]
##### addAll(...elements)
Adiciona vários elementos ao final de uma lista

# Removendo elementos da List
##### .remove
# Metódos Para List
 
 lenght - Retorna o tamanho da lista
 generate
 filled
 fold
 expanded
toSet( ) 

##### ... Spread Operator
Inclui elementos de outra List em uma List
```dart
  final numeros1 = [1, 2, 3, 4, 5];
  final numeros2 = [6, 7, 8];
  final novaLista = [...numeros1, ...numeros2, 9, 10];
  print(novaLista);
```
>novaLista = [1,2,3,4,5,6,7,8,9,10]

##### Collection for
 Um loop que apresenta novos valores na lista
```dart
  final numeros = [1, 2, 3, 4];
  final titulos = ['#0-Título', for (var numero in numeros) '#$numero-Título'];
  print(titulos);
```
>['#0-Título', '#1-Título', '#2-Título', '#3-Título', '#4-Título']





##### Collection if
Uma condição que pode apresentar novos valores na lista
```dart
  var promocao = true;
  var lanches = ['Batata', 'Hamburguer', if (promocao) 'Refrigerante'];
  print(lanches);
```


>['Batata' , 'Hamburguer' , 'Refrigerante']
