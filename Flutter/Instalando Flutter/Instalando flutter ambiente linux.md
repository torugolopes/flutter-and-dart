# Instalando programas essenciais
git 
vim
# Instalar e chavear o JDK
## Baixar os JDKs
Precisamos instalar várias versões do JDK, inicialmente instalaremos a versão 11 e a versão 8 do jdk, certifique-se que o seu sistema não tem nenhuma versão do jdk instalada, se tiver desinstalar usando o comando:
```
sudo apt-get purge openjdk*
```

Para baixar o JDK,no google pesquisar por jdk11 ou acessar no site da [oracle](https://www.oracle.com/br/java/technologies/javase/jdk11-archive-downloads.html) (fazer a mesma coisa para [versão 8](https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html))

Baixar a versão x64 compactada .tar.gz
Caso ainda não tenha uma conta na Oracle, será necessário criar uma.

Descompactar os arquivos na pasta /usr/local/lib/jdk

Podemos fazer isso usando o terminal:
```
cd Downloads
tar -xvzf jdk-11.0.15_linux-x64_bin.tar.gz
tar -xvzf jdk-8u202-linux-x64.tar.gz
```

mover para local/lib
```
cd /usr/local/lib
sudo mkdir jdk
cd jdk
sudo mv ~/Downloads/jdk-11.0.15 ./
sudo mv ~/Downloads/jdk1.8.0_202 ./
```

## Configurar Variáveis de Ambiente
```
vi ~/.bashrc
```

 Apertar I para inserir
 Inserir variáveis de ambiente: 
 
```
export JAVA_HOME=/usr/local//lib/jdk/current
export PATH=$PATH:$JAVA_HOME/bin
```
:wq! (para salvar e sair)


## Chaveando e navegando entre versões do JDK
No terminal, navegar até a pasta onde estão os JDKs
```
cd /usr/local/lib/jdk
```
Usar o comando ln -s "nomedapastaJDK"/ current para linkar a um jdk

```
sudo ln -s jdk-11.0.15/ current
```

Podemos verificar a versão do java chaveado usando o comando

```
  java -version
  ```

Para alterar para uma outra versão do JDK usamos 
```
sudo unlink current 
```

E agora podemos linkar uma pasta com uma versão diferente do JDK
```
sudo ln -s jdk1.8.0_202/ current
```



# Instalar o Android Studio
## Baixar e instalar o Android Studio
Pesquisar no google, download Android Studio ou acessar o [site](https://developer.android.com/studio?hl=pt&gclsrc=ds&gclsrc=ds), e fazer o download do Android Studio.
Descompactar o Android Studio dentro da pasta Documentos/Dev.

Botão direito na área de trabalho, opção criar novo lançador
- Colocar o nome como Android Studio
- Em comando navagar até Documentos/dev/Android-Studio/bin/studio.sh
- Colocar a imagem svg como ícone do aplicativo, que também está na pasta bin

![[Pasted image 20220607125257.png|425]]

Selecionar sim, para caixa de pergunta para adicionar o aplicativo no menu de lançadores também.

Abrir o Android Studio, não importar configurações.
Next, Next, Aceitar as licenças e fisnish

## Configurando o SDK do Android
Com o Android Studio aberto, clique em SDK manager
![[Pasted image 20220607145329.png]]
Copie o SDK location na nova janela, aqui no caso é:
/home/victor/Android/Sdk
![[Pasted image 20220607145705.png]]

Temos que adicionar o SDK location como variável no nosso PATH, entao 
```
vi ~/.bashrc
```
Tecle I para alterar o arquivo
Adicionar no final do arquivo
```
export ANDROID_HOME=/home/victor/Android/Sdk
export ANDROID_SDK_ROOT=/home/victor/Android/Sdk

```
Tecle esc 
:qw! (para sair e salvar)

Voltando para o Android Studio 
Em SDK plataforms, instale ao menos duas versões do Android
![[Pasted image 20220607150506.png]]

Na aba SDK tools, marque a opção Android SDK Command-Line Tools(latest)
![[Pasted image 20220607150624.png]]

Após isso clique em aplicar
Assim que acabar de aplicar as configurações do Android Studio, vá em plugins e instale o Plugin do Flutter
![[Pasted image 20220607151352.png]]

E também aceite a instalação do Plugin para Dart
![[Pasted image 20220607151434.png]]


## Configurando Path ADB Manager
```
vi ~/.bashrc
```

Adicionar no final do arquivo
```
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/plataform-tools
```

As suas variáveis de ambiente até aqui estarão mais ou menos assim:
![[Pasted image 20220607182147.png]]

## Configurando o Emulador Android
Dentro do Android Studio, selecionar a opção Virtual Device Manager:
![[Pasted image 20220607184737.png]]
Create Device
![[Pasted image 20220607184827.png]]
Phone / Pixel 5 / Next
![[Pasted image 20220607184935.png]]
Baixar e instalar Api level 31
![[Pasted image 20220607185036.png]]
Finish
![[Pasted image 20220607185441.png]]
# Emulando o device físico com 
Temos que habilitar o modo desenvolvedor no android.
1- Vá em configurações/Sobre o telefone/Número de compilação ou Versão do Android (essa opção pode variar dependendo do aparelho celular). Clicar várias vezes sobre ela até aparece, "Você agora é um desenvolvedor"

2- Ir em opções do desenvolvedor e ativar depuração usb, depuração USB (config. de segurança), Instalar via USB, Depuração sem fios

Para instalar o Scrcpy
[github scrcpy](https://github.com/Genymobile/scrcpy)
No terminal
```
sudo apt install scrcpy
```


# Instalando o FVM
Pré-requisitos
Instalar o [Homebrew](https://brew.sh/index_pt-br)
![[Pasted image 20220608155958.png]]

Use o comando no terminal:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Ao terminar de baixar o brew, vemos que ele nao está no nosso PATH, o terminal apresentará mais ou menos essa imagem, e precisamos seguir os passos descritos pós instalação para o adicionarmos no PATH
![[Pasted image 20220608160908.png]]
Ficará mais ou menos assim:
```
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/victor/.profile
```

```
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

```
sudo apt-get install build-essential
```

```
brew install gcc

```
Feche o terminal e abra novamente, certifique-se que o Brew está instalado digitando Brew no terminal.

Abra o arquivo ~/.bashrc
e adicione a seguinte variável no PATH
```
export PATH=$PATH:/home/linuxbrew/.linuxbrew/bin
```
Suas variáveis estão mais ou menos assim:
![[Pasted image 20220608205656.png]]

Agora estamos prontos para instalar o [FVM](https://fvm.app/docs/getting_started/installation)

![[Pasted image 20220608160217.png]]

Seguimos os comandos

```
brew tap leoafarias/fvm
```

```
brew install fvm
```

Agora temos o Fvm instalado em nosso ambiente
Podemos verificar as versões disponíveis para instalação usando:
```
fvm releases
```
Vamos instalar globalmente versão stable:
```
fvm global stable
```

Ao final da instalação,para que o fvm use a versão do flutter globalmente, precisamos adicionar essa variável no PATH, assim como sugerido
![[Pasted image 20220608172205.png]]
Temos entao em nosso PATH
![[Pasted image 20220608172407.png]]
no exemplo
```
export PATH=$PATH:/home/victor/fvm/default/bin
```

Fechamos o terminal, abrimos novamente e podemos rodar o flutter doctor
```
flutter doctor
```
> ![[Pasted image 20220608173306.png]]

Como sugerido, usar o comando:
```
flutter doctor --android-licenses
```
e aceitar todas as licenças

Para desenvolvimento flutter desktop, seguir com o comando:
```
sudo apt install clang cmake ninja-build libgtk-3-dev
```

Terminada a instalação,rodamos mais uma vez o flutter doctor
```
flutter doctor
```

> ![[Pasted image 20220608174038.png]]

Para navegar entre versões globalmente, só uma o comando fvm global "versãodesejada".

Exemplo:
```
fvm global 2.10.5
```


```
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/victor/.profile
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

Precisamo alterar uma configuração no VsCode
Ctrl + Shift + P 
abrir o Settings.Json
![[Pasted image 20220808101817.png]]
e adicionamos no vscode o path do dart no fvm cache 
![[Pasted image 20220808102751.png]]
