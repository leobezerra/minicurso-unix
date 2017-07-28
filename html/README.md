## Roteiro básico

Abaixo você encontrará a descrição de uma série de tarefas triviais presentes no cotidiano de quem trabalha com sistemas UNIX, organizados por tópicos.

Caso tenha dúvida na utilização de algum comando, consulte seu manual ou a tabela de comandos úteis encontrada neste [link](http://cheatsheetworld.com/programming/unix-linux-cheat-sheet/).

---

## Introdução

<!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/PctAg6mAxYU" frameborder="0" allowfullscreen></iframe> -->
<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='https://www.youtube.com/embed/PctAg6mAxYU' frameborder='0' allowfullscreen></iframe></div>

---

## <a href="slides">Slides</a>

Os slides que descrevem brevemente os comandos apresentados neste minicurso podem ser vistos abaixo, ou baixados [neste link](../keynote/handouts.pdf).
<!-- <iframe src="//slides.com/leobezerra/deck/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> -->
<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='//slides.com/leobezerra/deck/embed' frameborder='0' allowfullscreen></iframe></div>

---

# Exercícios 

Utilize os links abaixo para navegar pelos exercícios.

1. [Diretórios](#dirs)
1. [Arquivos](#files)
1. [Arquivos e fluxos](#streams)
1. [Compressão de arquivos](#compression)
1. [Busca](#seeking)
1. [Manipulação de fluxos](#manip)
1. [Processos](#processes)
1. [Permissões](#permissions)
1. [Executáveis](#running)

---

### <a name="dirs">Diretórios</a>

1. Abra o terminal e verifique em qual pasta ele é inicializado. 
1. Crie um diretório **minicursos** e um subdiretório **unix**.
1. Use o comando **ls** para verificar que o diretório e o subdiretório foram criados.

**Dica** -- é possível criar um diretório e seu subdiretório com apenas uma chamada ao comando **mkdir**. Também é possível listar um diretório recursivamente utilizando o comando **ls**.

[Voltar para os slides](#slides)

---

### <a name="files">Arquivos</a>

1. Com o auxílio de um editor de texto, crie dois arquivos de nome **arquivo1.txt** e **arquivo2**, contendo, respectivamente, as frases "*Este é o arquivo 1.*" e "*Este é o arquivo 2.*".
1. Mova ambos os arquivos para o diretório **minicursos**.
1. Crie um arquivo vazio **vazio.txt** no subdiretório **unix**.
1. Copie o arquivo **arquivo2** para o subdiretório **unix**.
1. Renomeie o arquivo **arquivo2** contido no subdiretório **unix** para **nao-vazio**.

[Voltar para os slides](#slides)

---

### <a name="streams">Arquivos e fluxos</a>

1. Baixe o arquivo [exemplo.in](../files/exemplo.in).
1. Crie um link simbólico chamado **exemplo** na pasta minicursos para o arquivo baixado no item anterior.
1. Visualize o conteúdo de **exemplo** sem usar um editor de texto.
1. Sem usar um editor de texto, copie as 5 primeiras linhas do arquivo apontado por **exemplo** para um novo arquivo **mini-exemplo.txt**, que deve ser criado dentro do subdiretório **unix**.
1. Sem usar um editor de texto, adicione as 5 últimas linhas do arquivo apontado por **exemplo** ao arquivo **mini-exemplo.txt**.
1. Gere um arquivo **mini-exemplo2.txt** idêntico ao arquivo **mini-exemplo.txt** sem usar os comandos **cp**, **mv**, **head**, **tail** ou um editor de texto. Assegure que os arquivos sejam idênticos sem usar um editor de texto.

[Voltar para os slides](#slides)

---

### <a name="compression">Compressão de arquivos</a>

1. Comprima o arquivo **mini-exemplo.txt** usando compressão Gzip.
1. Compare os tamanhos dos arquivos **mini-exemplo.txt.gz** e **mini-exemplo2.txt**.
1. Acesse o diretório pai do diretório **minicursos**.
1. Crie um pacote **tar** sem compressão chamado **minicursos.tar**, contendo o diretório **minicursos**.
1. Crie um pacote **tar** com compressão de arquivos Gzip chamado **minicursos.tar.gz**, contendo o diretório **minicursos**.
1. Crie um pacote **tar** com compressão de arquivos XZ chamado **minicursos.tar.xz**, contendo o diretório **minicursos**.
1. Crie um pacote comprimido Zip chamado **minicursos.zip**, contendo o diretório **minicursos**.
1. Compare o tamanho dos diferentes arquivos de nome-base **minicursos**.

**Dica --** para ver o tamanho de um arquivo, use uma das opções do comando **ls**. Para ver o tamanho de um diretório, consulte o manual do comando **du**.

[Voltar para os slides](#slides)

---

### <a name="seeking">Busca</a>

1. Busque no arquivo exemplo as palavras "*teste*" e "*testa*", sem usar um editor de texto.
1. Acesse sua pasta home (não confunda com o diretório **/home**).
1. Localize o arquivo cujo nome contenha a palavra **exemplo**.
1. Filtre a lista de ocorrências encontradas no item acima para mostrar apenas arquivos cuja extensão seja **txt**.
1. Busque, em todas as ocorrências encontradas no item acima, a palavra "*Este*".

**Dica --** para executar o item 5, utilize o comando **xargs**.

[Voltar para os slides](#slides)

---

### <a name="manip">Manipulação de fluxos</a>

1. Usando o arquivo **arquivo2** contido no diretório **minicursos** como base, gere um arquivo de nome **recortado.txt** no subdiretório **unix** contendo a frase "*Este é o 2.*".
1. Usando o arquivo **arquivo2** contido no diretório **minicursos** como base, gere um arquivo de nome **esfacelado.txt** no subdiretório **unix** contendo a frase "*Este arquivo*".
1. Usando o arquivo **arquivo2** contido no diretório **minicursos** como base, gere um arquivo de nome **tabulado.txt** no subdiretório **unix**, contendo o mesmo conteúdo de **arquivo2**, porém com separação de palavras por tabulação em vez de espaço.
1. Considerando o arquivo apontado por **exemplo**, liste em ordem alfabética os comandos aprendidos no minicurso.
1. Conte a quantidade de comandos identificados no item anterior.

**Dica --** para executar o item 3, utilize o comando **tr**.

[Voltar para os slides](#slides)

---

### <a name="processes">Processos</a>

1. Abra um editor de texto de sua preferência.
1. Identifique o código de processo da instância aberta do editor de texto.
1. Mate a instância aberta do editor de texto.
1. Liste, em ordem alfabética e sem repetições, os usuários que têm processos ativos no sistema. 
1. Conte a quantidade de processos ativos iniciados pelo usuário **root**.

[Voltar para os slides](#slides)

---

### <a name="permissions">Permissões</a>

1. Crie um arquivo de nome **arquivo_restrito** e configure suas permissões para que ninguém possa utilizá-lo para leitura, escrita ou execução. Verifique se você consegue realizar alguma destas operações.
1. Crie um diretório de nome **dir_restrito** e configure suas permissões para que ninguém possa visualizar seu conteúdo. Verifique se você consegue visualizar seu conteúdo após esta operação.
1. Altere as permissões do diretório **dir_restrito** para que seu proprietário (você) possa navegá-lo, mas não possa criar arquivos nele.

[Voltar para os slides](#slides)

---

### <a name="running">Executáveis</a>

1. Baixe o arquivo [exemplo.sh](../files/exemplo.sh). Configure suas permissões para que você possa executá-lo. Teste sua execução.
1. Configure a variável **PATH** para poder executar o script acima sem precisar digitar seu caminho. Faça esta configuração de forma que apenas a sessão em uso do terminal tenha sua configuração alterada.
1. Inicie uma nova sessão do terminal (nova aba ou janela) e configure a variável **PATH** para poder executar o script acima sem precisar digitar seu caminho, mas de forma que qualquer nova sessão do terminal seja afetada. Teste esta configuração na tela já em uso do terminal e também em uma nova janela.

[Voltar para os slides](#slides)

