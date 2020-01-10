# Guia De Instalacao do Java FX 
Um guia para fazer a instalação do JDK do Java e do JavaFX.

Esse guia foi testato no Ubunto 18.03 e usando o Java 11.

O mesmo guia, escrito em inglês pode ser encontrado em: https://openjfx.io/openjfx-docs/
Esse guia é somente uma versão em português do guia acima e com minhas palavras.

# Requisitos de Download:

- OpenJDK 11 (Pode usar o jdk do reporsitorio do Ubunto usando sudo apt intall openjdk-11-jdk)
- SDK 11 do OpenJFX (Obtido nesse link https://gluonhq.com/products/javafx/)
- JMods 11 do OpenJFX (Obtido no mesmo link acima)

# Organizando os arquivos
Feito os downloads extraia o SDK e o JMods e junte-os em uma mesma pasta.
O resultado fica-rá semelhante a essa estrutura:

  -javafx-sdk-11.0.2
   --javafx-jmods-11.0.2
   --legal
   --lib
   
Por fins de estetica e pra digitar menos, renomeie "javafx-jmods-11.0.2" para "jmods",
usarei esse nome daqui em diante.

# O problema

Caso exeute alguma aplicação feita com o JavaFX (Usarei como exemplo minha aplicação
Renomear) deverá ocorrer esse erro:

Erro: Não foi possível localizar nem carregar a classe principal Main
Causada por: java.lang.NoClassDefFoundError: javafx/application/Application

Esse erro indica que não existe a classe Application, isso ocorre pois não existe
nenhum modulo FX em sua JRE.

# Solução

Para adicioar os modulos nescessarios para executar essa aplicação adcione alguns
parametros a mais:

--module-path javafx-sdk-11.0.2/lib --add-modules=ALL-MODULE-PATH

Em "module-path" informe o local da pasta criado anteriormente.

Em "add-moules" deve ser informado os modulos a ser carregado, separando por virgula.
Entretando voce pode carregar todos os modulos do caminho especificado colocando
"ALL-MODULE-PATH".

O comando java deve ficar assim:

java --module-path javafx-sdk-11.0.2/lib/ --add-modules=ALL-MODULE-PATH -jar Renomear.jar

E a aplicação java deve ser executada com sucesso!
