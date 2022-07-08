---
layout: post
title: "Configuração do ambiente de desenvolvimento (Ubuntu 16.04)"
date:   2022-06-24 15:51:10 -0300
---

* __Instalar JDK17__
```
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt update
sudo apt install openjdk-17-jdk
java -version
```

* __Instalar Git (versão mais atual)__
Necessário apenas se for usar IntelliJ IDEA
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
        * Setar o valor da propriedade com o valor `"/usr/lib/jvm/java-17-openjdk-amd64/"`
        * Fechar todas as janelas do VSCode e abrir/criar um projeto Java para testar
        * Para saber se a configuração foi bem-sucedida, verifique se na aba "Java projects" aparece o seu projeto. 
          * Caso o projeto não apareça, abre e fecha o VSCode e espere o Gradle sincronizar. 
          * Se mesmo assim o projeto não aparecer na aba "Java projects", repita o processo (abrir e fechar) mais uma vez.
          * Pelo que temos observado, repetir duas vezes é o suficiente para a extensão Gradle sincronizar o projeto com sucesso.

* __(IDE alternativa) Instalar IntelliJ IDEA__
  * A IntelliJ IDEA é mais sofisticada que o VSCode, porém mais pesada.
  * É recomendada uma máquina com pelo menos 6GB de RAM para rodar a IDE satisfatoriamente.
  * Baixar a versão Community em https://www.jetbrains.com/idea/download/#section=linux
  * Descompactar o arquivo `.tar.gz` baixado
  * Copiar a pasta descompactada para um diretório adequado (por exemplo, `~/dev/`)
  * Pelo terminal, entrar no diretório `bin` da IDE:
  ```cd <dir-da-intellij>/bin```
  * Executar a IDE: `./idea.sh`
  * Criar um "desktop shortcut" para não precisar iniciar pelo terminal toda vez

