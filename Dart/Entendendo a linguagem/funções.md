A construção de uma função está dividida em três partes
1 - Tipo de retorno
2 - Nome da função
3 - Parâmetros (normais, nomeados, obrigatórios por default, opcionais)

(funções void nao tem retorno)
# Parâmetros de uma função
^54473a
**Os parâmetros podem ser...**
## ...obrigatórios (default)
```dart
  int somaInteiros(int num1, int num2) {
    return num1 + num2;
  }

  print(somaInteiros(1, 4));
```
>5

## ... opcionais e nomeados
{ } = Parâmetros nomeados
```dart
double somaDoubles({double? num1, double? num2}) {
  if (num1 != null && num2 != null) {
    return num1 + num2;
  } else {
    return 0.0;
  }
}

print('A soma de 6.1 + 3.2 é igual a: ${somaDoubles(num1: 6.1, num2: 3.2)}');

```
>A soma de 6.1 + 3.2 é igual a: 9.3

> [!INFO] Caracteristicas de uma função com parametros nomeados
>- Parametros nomeados são nullables por default
>- Parametros nomeados podem ser promovidos para non-null com checagem de null 
## ... opcionais com valor default
[ ] Significa que o parâmetro é opcional
```dart
int somaOpcional([int num1 = 0, int num2 = 0]) {
  return num1 + num2;
}
print('Soma de opcionais é igual: ${somaOpcional()}');
```
>Soma de opcionais é igual: 0
## ... obrigatórios e nomeados
Required = parâmetros obrigatórios
{ } = Parâmetros nomeados
```dart
double somaDoublesObrigatorio({required double num1, required double num2}) {
  return num1 + num2;
}

print(
      'A soma de 11.2 + 4.0 é igual a: ${somaDoublesObrigatorio(num1: 11.2, num2: 4.0)}');
```
>A soma de 11.2 + 4.0 é igual a: 15.2


## ... com valor default e nomeados
{ } = nomeados
```dart
int somaIntDefault({int num1 = 0, int num2 = 0}) {
  return num1 + num2;
}

print('A soma default é igual a: ${somaIntDefault()}');
```
>A soma default é igual a: 0

## ... misturados
- Parâmetros nomeados e obrigatórios não podem estar na mesma função
- Parâmetros nomeados ou obrigatórios devem ser declarados por útimo na função
[ ]= opcionais
{ }= nomeados
required = obrigatórios

```dart
void NormaisComNomeados(int num1, int num2, {String? nome, int? idade}) {}

NormaisComNomeados(1, 2, nome: 'Victor');
```
.
# Funções Arrow
Funções Arrow não tem corpo, o retorno delas é definido em uma única linha
```dart
  int somaInteiros(int num1, int num2) => num1 + num2;
  print(somaInteiros(5, 6));
```
.
# Funções anônimas
Funções anônimas podem estar jogadas ou associadas a uma variável.
A função anônima jogada no código deve terminar com ( ), pois é assim que a função é invocada.
```dart
  () {
    print('ola mundo');
  }();

```
>Olá mundo

Função anônima atribuida a uma variável:
Funções anônimas atribuidas a variáveis tem o nome de #clojure
```dart
  var olaMundo = (){
	  print('ola mundo');
	}()
  olaMundo()
```
>ola mundo

# Funções como parâmetros de outras funções


# typedef
Funções também podem receber outras funções como parâmetros.
[consultar vídeo parte3 antes e preencher o conteúdo](https://jornada.academiadoflutter.com.br/curso/jornada-dart-funcoes-e-colecoes/4537/25544)

por volta de min 14

