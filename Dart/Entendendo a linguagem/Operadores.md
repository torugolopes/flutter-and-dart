
# Relacionais

^f9d082

```dart
  final idade = 18;
  final sexo = 'masculino';

  if (idade >= 18 && sexo == 'masculino') {
    print('Pode entrar');
  } else {
    print('Não pode entrar');
```

```dart
>= MaiorIgual 
<= MenorIgual 
!= Diferente  
> MaiorQue  
< MenorQue  
== Igual  

```
# Lógicos

^0e37ed

```dart
  final idade = 18;
  final sexo = 'masculino';

  if (idade >= 18 && sexo == 'masculino') {
    print('Pode entrar');
  } else {
    print('Não pode entrar');
```
> 'Pode entrar'


  **Operador && (e):**
	- Todas as condições precisam ser verdade:
>TRUE && TRUE = TRUE
TRUE && FALSE = FALSE
FALSE && FALSE = FALSE
	




**Operador || (ou):**
	- Apenas uma das condições precisa ser verdade:

> TRUE && FALSE = TRUE
 TRUE && TRUE = TRUE
FALSE && FALSE = FALSE
FALSE && TRUE = TRUE





**Operador !( ) negação:**
	- Transforma o resultado no inverso:
```dart
  if (!(sexo == 'masculino')) {
    print('Pode entrar');
  } else {
    print('Não pode entrar!');
  }
```

>'Não pode entrar!'
# Ternários

^e892fd

É uma simplificação do if else


(condição) ? true : false
```dart
  final idade = 18;
  final eMaiorDeIdade = (idade >= 18) ? true : false;
  print(eMaiorDeIdade);
```

>true
