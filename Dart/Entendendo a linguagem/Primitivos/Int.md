Int são números inteiros
Int extends [[Num]]

# Declarando uma variável do tipo Int:


# Metódos:
##### .parse( )
Converte um elemento em int
```dart
int.parse(source)
```
```dart
  String numero = '2';
  var numeroNovo = int.parse(numero);
```

##### .tryparse( )
Tenta converter um elemento em int, se não for possível, retorna null
```dart
int.parse(source)
```
```dart
  String numero = '2a';
  var numeroNovo = int.tryParse(numero);
  print(numeroNovo);
```
>null
##### bitlength 
##### isEven
##### isOdd
##### hashCode
##### isFinite
##### isNaN
##### isNegative
##### runtimeType
##### abs()
##### ceil()
##### ceilToDouble()
##### clamp()
##### compareTo()
##### floor()
##### floorToDouble()
##### modPow()
##### remainder()
##### round()
##### roundToDouble()
##### toDouble()
##### toInt()
##### toRadixString()
##### toSigned()
##### toStringAsExponential()
##### toStringAsFixed()
##### toStringAsPrecision()
##### toUnsigned
##### truncate()
##### truncateToDouble() 





