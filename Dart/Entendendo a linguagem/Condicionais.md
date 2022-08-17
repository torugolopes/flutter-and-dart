# if

^fb83bc

```dart
  final idade = 18;
  if (idade >= 18) {
    print('Pode beber');
  }
```
>'Pode beber'
# if else

^473bca

```dart
  final idade = '';
  if (idade >= 18) {
    print('Pode tirar habilitação');
  }
  if (idade < 18) {
    print('Não pode tirar habilitação');
  } else {
    print('Idade não informada');
  }
```
>'Idade não informada'
# switch case

^d5ec21

```dart  
  final idade = 2;
  switch (idade) {
    case 0:
    case 1:
    case 2:
    case 3:
      print('Rescém-nascido');

      break;
    default:
      print('já grande');
      break;
  }
```
> 'Rescém-nascido'