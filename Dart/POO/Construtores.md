Os contrutores são funções que instanciam os objetos de uma classe, temos três tipos de construtores.
- Construtor default
- Construtor
- Factory 
# Construtor default
Todas as classes tem esse construtor por default
Ex:
```dart
class Pessoa {
  String? nome;
  int? idade;
  String? sexo;
}
```
```dart
  var paciente = Pessoa();
```
O objeto paciente foi instânciado na classe pessoa.

Podemos trabalhar o construtor default quando estamos criando a Classe da seguinte forma:
```dart
class Pessoa {
  String? nome;
  int? idade;
  String? sexo;

  //Construtor default
  Pessoa({required this.nome, required this.idade, required this.sexo});
}
```
A forma como definimos os parâmetros é a mesma de como definimos os [[funções#^54473a|parâmetros de uma função]], afinal construtores são funções.
Quando definimos os parâmetros do construtor default, fica bem mais fácil instâciarmos objetos
```dart
  var paciente = Pessoa(nome: 'Victor Lopes', idade: 31, sexo: 'Masculino');
  print(paciente.nome);
```
>Victor Lopes
# Construtor nomeado 
Podemos ter vários construtores dentro da nossa classe, fazemos isso usando construtores nomeados
```dart
class Pessoa {
  String? nome;
  int? idade;
  String? sexo;

  //Construtor default
  Pessoa({required this.nome, required this.idade, required this.sexo});
 
  //Contrutor nomeado		

  Pessoa.semNome(
      {String constructnome = 'Sem nome',
      required this.idade,
      required this.sexo}) {
    nome = constructnome;
  }
}
```
```dart
  var paciente = Pessoa.semNome(idade: 5, sexo: 'Masculino');
  print(paciente.nome);
```
>Sem nome

A forma como definimos os parâmetros é a mesma como definimos os [[funções#^54473a|parâmetros de uma função]], afinal construtores são funções.
# Factory
O construtor do tipo factory é usado quando precisamos implementar uma regra de negócio antes de instanciarmos o objeto 




[[funções#^54473a|Parâmetros de uma função]]
