#class #_ #static
Classe é uma representação de objetos do mundo real
Para criar uma classe, usamos a palavra reservada class
# Criando uma classe 
^3f612e
Aqui , criamos uma classe
```dart
  class Camiseta {}
```
## Uma classe é composta de...
### Atributos
Os atributos são as características do objeto, estes atributos são  definidos por variáveis dentro da classe.
#### Atributos de instância
Atributos de instância são acessados através do objeto instanciado
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? cor;
  String? marca;

```

```dart
  //Atributos de instância sendo acessados através do obj
  var camisetaNike = Camiseta();
  camisetaNike.tamanho = 'G';
```
#### Atributos de classe
Atributos de classe são atributos que tem acesso direto pela classe, não é necessário instanciar um novo objeto para ter acesso ao atributo de classe. Devem ser sempre que possível uma const. Usamos a palavra reservada static para definir um atributo de classe
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? cor;
  String? marca;

  //Atributo de Classe
  static const String nome = 'Camiseta';

```
```dart
  print(Camiseta.nome);
```
>Camiseta


### Comportamentos
Comportamentos é tudo que se pode executar com o objeto abstraído, comportamentos são definidos por funções dentro da classe.
#### Comportamentos de instância
Comportamentos de instância são acessados a partir do objeto instânciado
 
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? cor;
  String? marca;
	
  //Atributo de Classe
  static const String nome = 'Camiseta';
	
  //Comportamentos de instancia	
  String? tipoDeLavagem() {
    if (marca == 'nike') {
      return 'Não pode lavar';
    } else {
      return 'Pode lavar';
    }

```

#### Comportamentos de Classe
Os comportamentos de classe só tem acesso direto pela classe, eles usam a palavra reservada static. Metódos de classe só acessam atributos e metódos de classe também(que também usam a palavra reservada static).
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? cor;
  String? marca;
  
  //Atributo de Classe
  static const String nome = 'Camiseta';
	
  //Comportamentos de instancia	
  String? tipoDeLavagem() {
    if (marca == 'nike') {
      return 'Não pode lavar';
    } else {
      return 'Pode lavar';
    }
  //Comportamento de classe		  
  static String recuperarNome() => nome + ' comp de classe';
```
```dart
  print(Camiseta.recuperarNome());
```
>Camiseta comp de classe

# Atributos e Metódos privados
## Modificador privado
Quando o atributo ou metódo faz parte de uma regra de negócio, colocamos ele como privado, usamos o **_** (underline) antes do nome. No caso aqui, deixamos cor como atributo privado
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? _cor;  //cor atributo privado
  String? marca;
}
```
Para acessarmos ou modificarmos o atributo _cor, usamos o get (acessar) e o set(modificar).
## Getters e Setters
###  " _ " Criando Atributos e metódos privados
Toda vez em que o comportamento ou o atributo tem uma regra de negócio, é preciso defini-lo como privado, fazemos isso por meio do modificador de acesso  _ (underline) antes do atributo ou comportamento
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? _cor; // cor é um atributo privado
  String? marca;
}
```

Para acessar o atributo ou metódo privado usamos o Get, e para  definir uma regra de negócio para comportamento/metódo privado usamos o Set.(Setters não são a única forma de definir atributos e metódos privados)
### Set - definindo privados
Definimos uma regra de negócio para cor, no caso a cor não pode ser 'verde', se ela for definida dessa forma, o programa apresentará uma Exception.
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? _cor; // cor é um atributo privado
  String? marca;
  
	set cor(String? cor) {
    if (cor == 'verde') {
      throw Exception('Cor não pode ser verde');
    } else {
      _cor = cor;
    }
  }
}	
```
Continuamos definindo a cor do objeto camisa sem nenhuma mudança.
```dart
  var camisetaNike = Camiseta();
  camisetaNike.cor = 'azul';
 ```
### Get - acessando privados
Quando o atributo/comportamento é privado, ele também precisa passar por um get para acessar o comportamento. Assim:
```dart
class Camiseta {
  //Atributos de instancia
  String? tamanho;
  String? _cor; // cor é um atributo privado
  String? marca;

  set cor(String? cor) {
    if (cor == 'verde') {
      throw Exception('Não pode ser verde');
    } else {
      _cor = cor;
    }
  }

  String? get cor {
    return _cor;
  }

}
```
Continuamos definindo e acessando a cor do objeto camisa sem nenhuma mudança.
```dart
  var camisetaNike = Camiseta();
  camisetaNike.cor = 'azul';
  print(camisetaNike.cor);
```
> azul
