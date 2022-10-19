Objeto na programação é a representação de um objeto na vida real por meio da abstração, que é o processo pelo qual se isolam caracteristicas chaves do objeto referenciado a fim de sempre que for instanciado um novo objeto a partir de uma classe, ele carregue caracteristicas que representem este grupo de objetos.

Objetos são definidos por atributos e comportamentos. Sendo que:

Para atributos, são caracteristicas do objeto, como por exemplo uma camisa, a representação de atributos de uma camisa, seriam o tamanho, a cor, a marca... caracteristicas que compõe todas as camisas, e toda camisa precisa destas caracteristicas.

Para comportamentos ou metódos, são ações que o próprio objeto pode tomar ou que um agente externo pode fazer com o objeto, seguindo o exemplo da camisa, podemos lavar uma camisa, e essa ação irá limpar a camisa, porém podem haver regras de negócio que estão implicitas no comportamento, a camisa de algodão se lavar com sabão estraga, ou a partir de determinado número de lavagens, determinada marca irá desbotar a estampa. No objeto pessoa, a pessoa faz aniversário e isso aumenta sua idade, a pessoa pode casar, são comportamento relacionados ao objeto. 

Instanciando uma classe:
```dart
class Pessoa {
	String? nome;
	int? idade;
	bool casado = false;
}
```

Instanciando um objeto a partir de uma classe:
```dart
Pessoa pessoa1 = Pessoa();
```









Construtores, 
constroi o objeto a partir da classe
O padrão é colocar o contrutor sempre no topo da nossa classe 

o padrao é: 
1 construtores
2 atributos
3 metódos 


contrutor simples, já vem por padrão, especificando ou não, tem o mesmo resultado 
Pessoa();

Pessoa({required this.nome, required this.idade}){
	
}


this.variavel = quando usamos o *this.* estamos fazendo referencia a variável instanciada na nossa classe 



construtor nomeados servem quando querendo criar um objeto mas de uma maneira predefinida






getters e setters 

atributos privados são identificados no código com o _  antes da variável. Usamos atributos privados quando precisamos de uma regra de negócio para ter acesso a esse tipo de variável. Uma vez que a variável é privada, acessamos ela através de getters e setters.
O get, sempre que precisamos ler está variável, e o set sempre que precisamos alterar essa variável.


set dinheiro(double valor){
	_dinheiro = valor
}


Como tratamos valores nulos em atributos de classe?
atributos nullable (curso sttarto.dev, ler)



Atributos e metódos estáticos
São atributos que pertencem a classe e não aos objetos instanciados a partir da classe.

nao podemos acessar atributos de um objeto a partir de um static, afinal, não sabemos a que objeto estariamos nos referindo, então statics (atributos e metódos da classe) acessam apenas statics

porém atributos e metódos dos objeto podem acessar statics (atributos e metódos da classe) 

Chamando atributos da classe e não do objeto
Statics 



```dart


late String cpf;
```
Vamos supor que no nosso cadastro de pessoas, toda pessoa deve ter um CPF, mas no momento do cadastro nao temos o CPF, podemos usar o recurso *late* do dart.

Late significa depois, essa variável pode será inicializada depois, mas ela sempre deve ser inicializada antes de ser utilizada, se tentarmos ler uma variável late que ainda não foi preenchida precisamos fazer um tratamento de erros para que o nosso programa nao apresente erro para o usuário.

A diferença entre null e late, é que com o late não precisamos estar fazendo a verificação, entendemos que o valor null tem o seu valor também, estamos dizendo que todas as pessoas precisam se cadastrar e tem CPF.


lete ou get (diferença de comportamento)
```dart
late temperatura = medirTemperatura();

double get temperatura2 => medirTemperatura(); 

```

Herança **é um princípio de orientação a objetos, que permite que classes compartilhem atributos e métodos, através de "heranças"**. Ela é usada na intenção de reaproveitar código ou comportamento generalizado ou especializar operações ou atributos.


A classe Cachorro está herdando Animal, isso significa que a Classe cachorro terá todos os metódos e atributos da classe Animal
```dart
class Animal {

String? nome;

int? idade;

}
 

class Cachorro extends Animal {

void latir() {

print('au au');

}

}
```
Vantagens da herança
***** escrever ainda



Reescrita de metódos,
Temos a classe animal, e a classe Cachorro é filha de Animal,  instanciamos um objeto a partir da classe Cachorro e ela herda os atributos e metódos de Animal, Cachorro tem o metódo dormir, porém, os objetos instanciados a partir da classe cachorro Cachorro, e apenas da classe Cachorro dentre todas as outras classe que são filhas de Animal, ao executar o metódo dormir, objetos instanciados a partir de Cachorro precisam também roncar, então precisamos reescrever esse metódo para a classe Cachorro.
Nota que o retorno e o nome do metódo deve ser o mesmo declarado na classe pai
```dart
void main() {

	Cachorro cachorro1 = Cachorro();

	cachorro1.dormir();

}

class Animal {
	String? nome;
	int? idade;
  
void dormir() {
	print('Dormiu');
	}
}

class Cachorro extends Animal {
	void latir() {
	print('au au');
}

  
void dormir() {
	print('Dormiu roncando muito');
	}
}

```
> Dormiu roncando muito

Podemos reescrever metódos dentro do próprio dart, por exemplo, em dart tudo é um objeto, e nossa classe Cachorro vem de Animal, e animal vem de Object, onde temos o metódo String     (aula reescrita de metódos sttarto.dev)

Usando metódos da Super Classe após reescrita do próprio metódo
Quando reescrevemos o metódo, pode ainda assim chama o metódo da classe pai com a palavra reservada super.
Normalmente só usamos o super quando estamos escrevendo o próprio metódo dentro dele mesmo
Como no exemplo:
```dart
class Animal {

	String? nome;
	int? idade;
	
	void dormir() {
		print('Dormiu');
	}
}

class Cachorro extends Animal {
	void latir() {
	print('au au');
}
@override
void dormir() {
	super.dormir();
	print('Dormiu roncando muito');
}
```

Reescrevendo metódos construtores
Dada a classe Animal, implementamos um construtor nela

```dart
class Animal {
	Animal(this.nome, this.idade);
	String nome;
	int idade;
	void dormir() {
		print('Dormiu');
	}
}
```
Quando vamos declarar a classe Cachorro que tem como pai Animal, precisamos implementar um construtor que faça uma ponte para a classe Animal referenciando o nome e a idade
Nosso contrutor da classe cachorro só serve nesse exemplo para receber os parametros de idade e nome da classe pai, obviamente podendo receber mais parametros que iriam compor a classe Cachorro.
```dart
class Cachorro extends Animal {
	Cachorro(String nome, int idade) : super(nome, idade) {
		print('Criou o cachorro $nome');
}

	void latir() {
		print('au au');
	}
	@override
	void dormir() {
		super.dormir();
		print('Dormiu roncando muito');
	}

}
```

Agora podemos instanciar um objeto Cachorro
```dart
void main() {
	Cachorro cachorro1 = Cachorro('Rex', 8);
	cachorro1.dormir();
}
```

>Criou o cachorro Rex
   Dormiu
   Dormiu roncando muito


encapsulamento - quando temos uma estrutura complexa que é deixada muito mais simples para o usuário final, escondemos a complexidade e entregamos o resultado. Uma outra caracteristica do encapsulamento é a ocultação da informação, exemplo, para enviar um email, o usuário final não precisa saber o servidor smtp, ele precisa enviar o email, e o gerenciador de email entrega isso de forma encapsulada para ele 