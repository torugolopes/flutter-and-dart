variável?.metódo
Se nao for nulo, executa o metódo
```dart
String? nome;
void main() {
  nome = 'Victor';
  print(nome?.toUpperCase());
}

```
>'VICTOR'

<br><br><br>

E também podemos usar o conditionalProperty em conjunto com o [[nullAwareOperator]]

```dart
String? nome;
void main() {
  print(nome?.toUpperCase()?? 'ViCtOr lopes');
}
```
>''ViCtOr lopes''