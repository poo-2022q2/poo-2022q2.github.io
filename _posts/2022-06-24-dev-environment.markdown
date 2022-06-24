---
layout: post
title:  "Configuração do ambiente de desenvolvimento (Ubuntu 16.04)"
date:   2022-06-24 15:51:10 -0300
---

* __Instalar JDK11__
```
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt update
sudo apt install openjdk-lts
java -version
```

* __Instalar Git (versão mais atual)__
```
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
git --version
```
    * __Configurar commits no Git__
    ```
    git config --global user.name "Fulano de Tal"
    git config --global user.email fulanodetal@exemplo.br
    ```

* __Instalar Visual Studio Code__
    * Baixar arquivo `.deb` em https://code.visualstudio.com/
    * Abrir o terminal no diretório em que foi feito o download e instalar:
    ```sudo apt install ./<arquivo deb>```

* __Configurar VSCode__
    * Instalar extensão "Extension Pack for Java" (vscjava.vscode-java-pack)
    * Instalar extensão "Gradle for Java" (vscjava.vscode-gradle)
    * Configurar JAVA_HOME para o plugin Gradle
        * Abrir configurações VSCode (CTRL+,)
        * Procurar `java.jdt.ls.java.home`
        * Setar o valor da propriedade com `/usr/lib/jvm/java-11-openjdk-amd64/`
        * Fechar todas as janelas do VSCode e abrir um projeto Java para testar

* __(IDE alternativa) Instalar IntelliJ IDEA__
    * Baixar a versão Community em https://www.jetbrains.com/idea/download/#section=linux
    * Descompactar o arquivo `.tar.gz` baixado
    * Copiar a pasta descompactada para um diretório adequado (por exemplo, `~/dev/`)
    * Pelo terminal, entrar no diretório `bin` da IDE:
    ```cd <dir-da-intellij>/bin```
    * Executar a IDE: `./idea.sh`
    * Criar um "desktop shortcut" para não precisar iniciar pelo terminal toda vez

