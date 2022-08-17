((Faça se não for nulo) ?? (faça se for nulo))
```dart
String? nome;
void main() {
  var sobrenome = 'Lopes';
  var nomeCompleto = (nome ?? 'Victor ') + sobrenome;
  print(nomeCompleto);
}

```
>'Victor Lopes'