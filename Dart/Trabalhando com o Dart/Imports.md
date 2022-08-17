Há duas formas de fazer os imports

**Import a partir do caminho relativo**  ^importrelativo

![[Pasted image 20220509182815.png]]
import 'caminho_a_partir_da pasta_atual'
Neste caso: ^e5e929
```dart
import 'arquivosImport/somaInteiros.dart';
```
lembre-se que com dois pontos(..) voltamos um nível da pasta

**Import a partir do package**  ^importpackage

import package:nome_do_projeto/caminho_do_package
Neste caso
```dart
import 'package:imports/imports/arquivosImport/somaInteiros.dart'
```

**Alias para imports** ^aliasparaimports

Quando importamos funções e metódos que tem nomes iguais, usamos alias na importação
import 'caminho_a_partir_da pasta_atual' as alias_do_import
Nesse caso 
```dart
import 'arquivosImport/somaInteiros.dart' as nova_soma;
```
O padrão de escrita do alias é camel_case
Para invocarmos uma função do package importado que usa um alias fazemos assim:
alias.method
Ex:
```dart
nova_soma.somaInt(1,2)
```