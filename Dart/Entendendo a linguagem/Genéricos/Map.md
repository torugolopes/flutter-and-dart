# O que é um Map?
É uma representação de chave e valor
Uma das estruturas mais importantes dentro do dart, quando trabalhamos com serviços Rest, onde um JSON se tranforma em um Map

# Formas de declarar um Map
```dart
  Map pessoas = <String, String>{};
  var funcionarios = <String, String>{'nome': 'João'};
  Map <String,String>? pacienteNullSafety = null;
  Map <String?,String?> pacienteNullSafety = {};

```
```dart
  var mapa = <String, Object>{
    'nome': 'Rodrigo',
    'cursos': [
      {
        'nome': 'Curso Flutter',
        'desc': 'um bom curso'
      },
      {
        'nome': 'Curso Php',
        'desc':'Curso Php beckend'
      }
    ]
  };
```
>
# Acessando elementos do Map
```dart
  var funcionarios = <String, String>{'nome': 'João'};
  print(funcionarios['nome']);
```
>João
# Adicionando elementos no Map
Map.putIfAbsent ('key', ( )=>'value')
```dart
  var funcionarios = <String, String>{'nome': 'João'};
  funcionarios.putIfAbsent('profissao', () => 'Eletricista');
  print(funcionarios);
```
> {nome: João, profissao: Eletricista}
# Atualizando elementos no Map
Map.update('key', (value)=> 'new value' )
```dart
  var funcionario = <String, String>{'nome': 'João'};
  funcionario.update('nome', (value) => 'Maria');
```
>funcionario = {nome: Maria}


Atualizar valor, mas se a chave não existir, adicionar chave e valor

Map.update('key', (value)=> 'new value', ifAbsent: ( ) 'value if absent')
```dart
  var funcionario = <String, String>{'nome': 'João'};
  
  funcionario.update('profissao', (value) => 'eletricista',
      ifAbsent: () => 'eletricista');
```
>funcionario = {nome: João, profissao: eletricista}
# Laços de Repetição com Map
Map é compatível com todos os laços de repetição, eles seguem um padrão um pouco diferente quando aplicamos um laço, afinal o Map é composto de chave e valor.
Consulte [[Laços de Repetição]] para outros exemplos.
## varrendo chaves e valores
```dart
  var funcionario = <String, String>{
    'nome': 'Victor',
    'Idade': '31',
    'Cargo': 'Analista',
    'Turno': 'Diurno'
  };

  for (var dado in funcionario.entries) {
    print('Chave ${dado.key} : Valor ${dado.value}');
  }
```
>Chave nome : Valor Victor
Chave Idade : Valor 31
Chave Cargo : Valor Analista
Chave Turno : Valor Diurno
## varrendo chaves
```dart
  var funcionario = <String, String>{
    'nome': 'Victor',
    'Idade': '31',
    'Cargo': 'Analista',
    'Turno': 'Diurno'
  };

  for (var key in funcionario.keys) {
    print('Chave $key');
```
>Chave nome
Chave Idade
Chave Cargo
Chave Turno
## varrendo valores
```dart
  var funcionario = <String, String>{
    'nome': 'Victor',
    'Idade': '31',
    'Cargo': 'Analista',
    'Turno': 'Diurno'
  };

  for (var value in funcionario.values) {
    print('Valor: $value');
```
>Valor: Victor
Valor: 31
Valor: Analista
Valor: Diurno
# Interables com Map
Map é compatível com todos os interables, eles seguem um padrão um pouco diferente quando aplicamos um metódo de interable ao Map, afinal o Map é composto de chave e valor.

Consulte [[Interables]] para outros exemplos.
```dart
  var funcionario = <String, String>{
    'nome': 'Victor',
    'Idade': '31',
    'Cargo': 'Analista',
    'Turno': 'Diurno'
  };

  funcionario.forEach((key, value) {
    print('$key : $value');
  });

```
>nome : Victor
Idade : 31
Cargo : Analista
Turno : Diurno

