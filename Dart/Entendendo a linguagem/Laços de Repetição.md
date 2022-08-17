# Laços de Repetição
## for 
for (var ; condição ; incremento){ }
```dart
  var numeros = [];
  for (var i = 0; i < 10; i++) {
    numeros.add(i);
  }
  print(numeros);
```
>[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

## for in 

^53ca65

Percorre todos os elementos de uma lista
```dart
  var numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  for (var numero in numeros) {
    print(numero);
  }
}
```
>1
>2
>3
>4
>5
>6
>7
>8
>9
>10
## while
Executa enquanto a condição for verdade
```dart
  var indice = 1;
  do {
    print('O indice está em $indice');
    indice++;
  } while (indice < 5);
```
>0
>1
>2
>3
>4

## do while
Executa ao menos uma vez, mesmo que a condição não seja verdadeira
```dart
  var indice = 1;
  do {
    print('O indice está em $indice');
    indice++;
  } while (indice < 5);
```


# Ferramentas para o Laço
## break
```dart
  var numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  for (var i = 0; i < 10; i++) {
    print(i * 10);
    if (i * 10 >= 50) {
      print('$i é maior ou igual a 50');
      break;
    }
  }
```
>10
>20
>30
>40
>50
>'50 é maior ou igual a 50'
## continue
```dart
  for (var i = 0; i < 10; i++) {
    if (i == 5) {
      print('pulei um');
      continue;
    }
    print(i);
  }
```
>0
>1
>2
>3
>4
>'pulei um'
>6
>7
>8
>9
