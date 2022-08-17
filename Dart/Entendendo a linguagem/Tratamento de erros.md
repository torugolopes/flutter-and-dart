# try catch

^116cb5

error = o tipo de erro apresentando 
stackTrace = onde exatamente se iniciou o problema
```dart
  var idade = '38 anos';
  try {
    int.parse(idade);
  } catch (error, stackTrace) {
    print('Não foi possível converter idade');
    //print(erro);
    //print(stackTrace);
  }
```
>Não foi possível converter idade

# Ações específicas para erros específicos

^eae2a6

 **on** para definir a exceção específica
 **catch** para tratar essa exceção específica
O tratamento das exceções devem ser tratados por nível, todas as exceções extends Exceptions

```dart
  var idade = '38';
  
String? nome;
  try {
    int.parse(idade);
    nome!.toUpperCase();
  } on FormatException {
    print('Erro, ao converter idade');
  } on TypeError catch (e) {
    print('Erro no nome');
  } catch (e) {
    print('Erro ao executar programa');
  }
```
>Erro no nome

# Exceptions

^780381

FormatException
TypeError
# Forçando um erro 

^74b084

```dart
  var idade = '38';
  try {
    int.parse(idade);
    if (int.parse(idade) == 38) {
      throw Exception();
    }
  } on FormatException {
    print('Erro, ao converter idade');
  } on Exception {
    print('Esse programa não é para essa idade');
  } catch (e) {
    print('Erro ao executar programa');
  }
```
>Esse programa não é para essa idade
# O cara que sempre será executado

^3cfa47

```dart
  var idade = '38';
  try {
    int.parse(idade);
    if (int.parse(idade) == 38) {
      throw Exception();
    }
  } on FormatException {
    print('Erro, ao converter idade');
  } on Exception {
    print('Esse programa não é para essa idade');
  } catch (e) {
    print('Erro ao executar programa');
  } finally {
    print('O teste acabou');
  }
```
>Esse programa não é para essa idade
O teste acabou
