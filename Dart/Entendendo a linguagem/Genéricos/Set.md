# O que é um Set
Set é uma lista de valores que não permite valores duplicados

# Formas de declarar um Set
```dart
  var numerosSet = Set();
  var numerosSet2 = <int?>{};
  var numerosSet3 = {1, 2, 3, 4, 5};
```


# Acessando  elementos do Set
Set.elementAt(indice)
```dart
   var numerosSet = {1, 2, 3, 4, 5};
   print(numerosSet.elementAt(2)); 
```
>3
# Removendo elementos do Set
# Metódos do Set



.difference - ver as diferenças entre dois sets 
trás os números do primeiro Set que não tem no segundo Set
.union -  juntar dois Sets nao permitindo duplicados 
.intersection - mostra os valores em comum entre dois Sets
.lookup - busca um valor no Set, se o valor existir, ele retorna o próprio valor, se o valor não existir, ele retorna null 
.
