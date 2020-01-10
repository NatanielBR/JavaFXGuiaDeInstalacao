# Guia Netbeans

Esse guia orienta a como desenvolver aplicações Java usando o JavaFX no Netbeans.

O mesmo guia, escrito em inglês, pode ser encontrado em: https://openjfx.io/openjfx-docs/

Esse guia é somente uma versão em português do guia acima e com minhas palavras.

# Em outro Guia...

Utilizando o guia de instalação (https://github.com/NatanielBR/JavaFXGuiaDeInstalacao)
você irá ter uma pasta chamado javafx-sdk-11.0.2 .

# Criando uma biblioteca de classes

Abra o netbeans.

Vá em Tools -> libraries e clique em "New Library".

Informe o nome e confirme.

Na aba "Classpath" clique em "Add JAR/Folder" e localize a pasta "javafx-sdk-11.0.2"
e dentro dessa pasta abra a pasta "lib" e selecione todos os arquivos .jar dessa pasta.

Clique em Ok para concluir.

# No projeto

Em seu projeto abra o menu de Propriedades.

Escolha a opção Libraries e adicione sua Library recem criada.

Não saia dessa janela, agora escolha a opção Run.

Na aba "VM Options", coloque:

--module-path <caminho absoluto da pasta javafx-sdk-11.0.2>/lib --add-modules ALL-MODULE-PATH

Em module-path coloque o caminho absoluto para a pasta e depois coloque /lib .

Agora clique em OK e execute sua aplicação em JavaFX.
