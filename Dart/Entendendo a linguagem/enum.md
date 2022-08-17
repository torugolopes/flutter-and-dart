Usabilidade 
Quando criamos valores estáticos que representam elementos, usamos o enum, em termos de usabilidade, os valores estáticos serão sempre os mesmo.
O enum deve ficar fora da função void main 
# Declarando um enum 
```dart
void main() {
  var cor = Cores.vermelho;

}
enum Cores { vermelho, azul, amarelo, verde }
```
enum nomeEnum{ }

# Switch Case e enum
Para saber mais sobre [[Condicionais#^d5ec21|Switch Case..]]
Quando vamos comparar todos os casos de um enum, podemos usar o Switch Case, o próprio Dart irá sugerir que todas as possibilidades sejam preenchidas
![[Pasted image 20220509191531.png]]
Ao parar o cursor de texto sob a paravra switch e pressionar as teclas ctrl + . , o dart irá preencher todas a possibilidades do enum:
![[Pasted image 20220509191748.png]]
Add missing cases:
![[Pasted image 20220509191832.png]]



Acessando os elementos de enum
print(Cores.azul.name)


coverter 
var corAzul215 = Cores.values.byName('azul');
print(corAzul215)

Metódos de enum
asMap()
var coresMap = Cores.values.asMap();
print(coresMap);

asNameMap( )
var coresNameMap = Cores.values,asNameMap();
print(coresNameMap);



vantagem de converter para um map, se buscar um enum que nao existe, o programa da erro, se buscar dentro de uma lista um valor que nao existe, ele retorna null 