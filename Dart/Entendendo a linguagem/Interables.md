# forEach 

^06b819

Esse metódo não deve ser usado com requisições assincronas
Em caso de requisições assincronas usar o [[Laços de Repetição#^53ca65|for in]]


```dart
List.forEach((element) {});
```

forEach irá percorrer todos os elementos da lista e irá realizar alguma ação a cada elemento

```dart
  var numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  numeros.forEach((numero) => print(numero + 5));
```
>6
>7
>8
>9
>10
>11
>12
>13
>14
>15

```dart
  var numeros = [1, 2, 3];
  numeros.forEach(print);
```
>1
>2
>3

# map

^9103c4

Map retorna um novo interable

```dart
numeros.map((e) => null)
```

```dart
  var numeros = [1, 2, 3, 4];
  var numString = numeros.map((numero) => 'número: $numero');
  print(numString);
```
>(número: 1, número: 2, número: 3, número: 4)

Voce pode usar o comando [[toList|toList( )]] para voltar a trabalhar com uma lista
# reversed

^0b42ec



```dart
List.reversed
```

```dart
  var numeros = [1, 2, 3, 4];
  print(numeros.reversed);
```
>(4, 3, 2, 1)

Reversed retorna um interable, para voltarmos a ter uma lista, podemos usar [[toList|toList( )]]
# skipWhile

^942ebb


```dart
List.skipWhile((value) => false)
```

```dart
  var numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  print(numeros.skipWhile((numero) => numero <= 5));
```
>(6, 7, 8, 9, 10)

Transforma a sua lista em um interable, você pode usar o comando [[toList|toList( )]] para transforma-lo em uma lista novamente.
# takeWhile

^3df387


#takeWhile
```dart
List.takeWhile((value) => false)
```


```dart
  var numeros = [1, 2, 3, 4, 5, 6, 7];
  print(numeros.takeWhile((numero) => numero < 5));
```
>(1,2,3,4,5)

Ele transforma nossa lista em um interable


# where

^7754fb


```dart
List.where((element) => false);
```

```dart
  var numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  print(numeros.where((numero) => numero >=5));
```

>(5, 6, 7, 8, 9, 10)

Ele transforma nossa lista em um interable, podemos usar o [[toList|toList( )]] para transforma-lo em uma lista novamente.
