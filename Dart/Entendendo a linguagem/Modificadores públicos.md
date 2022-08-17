var
final 
const 

modificadores definem o comportamento de uma variável,
var , var é usado localmente e por padrão já inferimos o tipo da variável assim que declaramos ela
```dart
var nome = 'Victor';
```

final - 
não podem ser alteradas depois de inicializadas
são definidas em tempo 
torna a variável impossivel de ser alterada, só pode ser atribuida o valor uma vez, a imutabilidade, ela é iniciada em momento de execução, final pode receber valores de outra variável final, var e também const

const - torna a variável impossivel de ser alterada, só pode ser atribuida o valor uma vez, a imutabilidade, ela só é iniciada em momento de compilação, const só pode receber valores de outra variável const