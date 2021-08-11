<img src="https://hermes.digitalinnovation.one/articles/cover/effe8a64-c52a-4983-aedb-91b5e432027f.png" alt="image-20210810031215647" style="zoom:25%;" />


<h1>Aprendendo Git</h1>

O Git é um sistema de controle de versões distribuído, gratuito e código aberto, projetado para trabalhar desde projetos pequenos a grandes. Por ser distribuído, quer dizer que não existe um repositório central oculto que controla todo o código. Em cada colaborador, vai estar salvo o código e seu histórico de versões. Se trata de uma ferramenta que entrega velocidade e eficiência — por isso é unanimidade no que se propõe. Sua mágica é facilitar o trabalho em equipe, você e sua equipe terá total controle sobre o que cada um implementa nas linhas de um projeto; ou seja, criando "branchs", tipo de ramificações do código em que cada membro exerce sua parte e em pontos cruciais se faz um "merge", ou seja, mescla essas ramificações em um só código.

*I'm an egotistical bastard, so I name all my projects after myself. First Linux, now git.*

— Linus Torvalds

# Pré-requisitos para usar o Git

------

Formalmente, não existe nenhum pré-requisito para começar a usar essa ferramenta. Você pode baixar, aprender seus comandos e começar a utilizar. Mas durante meu estudo eu percebi que alguns conhecimentos prévios foram imprescindíveis para melhor compreender a ferramenta. O Git é todo baseado em linha de comando, ou seja, roda diretamente em um Terminal. Convém, portanto, aprender alguns comandos básicos para o terminal (seja do Prompt de Comando em Windows, ou seja do Terminal Unix). Se você usa o Windows, eu recomendo fortemente o download do terminal [Cmder](https://github.com/cmderdev/cmder/releases/download/v1.3.18/cmder.zip). Baixando sua versão mais completa, você poderá utilizar tanto os comandos de terminal Unix, como do Prompt de Comando. Aumentando seu leque de possibilidades de comando.

Os principais comandos a se aprender são:

**cd :** é a forma como você vai indicar para o terminal sua navegação pelas pastas *(diretórios)*

**dir :** é como você vai perguntar ao terminal quais são os arquivos que existem no diretório

**ls** : o mesmo que o comando **dir,** contudo, usado para Unix. O Git aceita ambos os comandos. O **ls** é mais completo, você pode combinar com ele o "-a" por exemplo e listar também arquivos e diretórios ocultos

**cd .. :** comando que indica que você quer voltar uma página

**mkdir "**nome da pasta" **:** é como você vai pedir ao terminal que crie uma pasta onde você está

**rmdir "**nome da pasta" : é como você vai pedir ao terminal para remover uma pasta vazia. Para excluir uma pasta que contém arquivos ou outros diretórios dentro, você precisa escrever após o **rmdir,** na mesma linha, o comando "/s"

**rm -r** : mesma função do **rmdir /s** — ****utilizada em terminais Unix

**echo "**mensagem" : é como você pede ao terminal para exibir uma mensagem nele mesmo

**echo** **"**mensagem" *(opcional)* ">" *(ou ">>" caso o arquivo já existe e você deseja escrever em uma nova linha dentro dele)* "nome do arquivo.tipo" : criar um arquivo de tipo específico e gravar algo dentro dele

**touch** "nome do arquivo" : criar aquivo. Também é possível especificar o tipo

**clear** : como você pede ao terminal para limpar tudo que tem escrito nele

**move** "arquivo" "caminho para o diretório onde você quer movê-lo"  : mesma função do recortar que você provavelmente está acostumado.

**copy** "arquivo" "caminho para o diretório onde você quer copiá-lo" : mesma função do copiar que você provavelmente está acostumado

setas **(cima)** ou **(baixo)** : o terminal vai mostrar no cursor o histórico de comandos que você já deu para ele durante a sessão

# Iniciando no Git

Após fazer o [download](https://git-scm.com/downloads) do Git e instalar ele em sua máquina, procure pelo executável **Git Bash**. Ele também vai mostrar em seu computador outros executáveis, como o **Git GUI**, que é o Git em uma interface gráfica, e o **Git CMD**, um terminal parecido com o Prompt de Comando. Por incrível que pareça, para o aprendizado é melhor você ignorar o programa com interface gráfica e partir para o **Git Bash.** A interface gráfica nesse momento vai atrapalhar mais do que ajudar. Você também vai perceber que ao usar o Windows Explorer, em qualquer pasta que tiver ao clicar com o botão direito surgirão novas opções. São elas: **Git Bash here** e **Git GUI here**. É uma forma mais simples caso você não deseje navegar pelo termina do Git até a pasta que quer adicionar como repositório — basta clicar em **Git Bash here** que ele vai abrir o Git já na pasta que você indicou.

### Exercício para fixar os comandos acima indicados e deixar tudo pronto para iniciar o Git

- Abrir o terminal do seu computador, seja no Prompt de Comando ou, de preferência, no Cmder. Ele provavelmente vai iniciar na pasta do seu usuário. Tente navegar entre os diretórios, vá até a pasta de Documentos e nela crie uma nova pasta chamada "aprendendo-git". Nela, você vai criar mais três pastas, uma com seu nome, outra com outro nome (para simular duas pessoas no mesmo projeto mais adiante) e a última com o nome "Servidor".
- Na pasta com seu nome, crie um novo arquivo chamado README do tipo .md (tipo convencional de arquivos readme, são arquivos de texto). No momento em que você estiver criando esse novo arquivo, também adicione uma frase dentro dele: "Hello, world!".
- Retorne para a página anterior, liste os arquivos, remova e adicione as pastas novamente para testar os comandos. Quando terminar a brincadeira, apague todos os diretórios. Se prepare para o teste final.
- Dentro do diretório "aprendendo-git" crie um arquivo chamado "arrumando_a_casa" do tipo .bat (tipo de arquivo que executa no Prompt de Comando). Para a primeira linha, use o comando **@echo off** (teste depois com e sem ele para perceber as diferenças). Use o comando dado acima para escrever dentro dele linhas de código para realizar a criação dos diretórios que você acabou de excluir, contudo, para criar o arquivo .md dentro da pasta com seu nome você deve seguir a instrução abaixo. Basta escrever dentro desse arquivo o mesmo que você escreveria dentro do terminal.
- 🚩 Você pode também abrir o programa do Bloco de notas e arrastar para dentro dele o arquivo .bat, assim você tem uma visualização melhor sobre o que tem nele e você pode editar as linhas de comando. Com o terminal no mesmo diretório do .bat, execute-o digitando no seu terminal o nome do arquivo. Após verificar dentro do próprio terminal ou dar uma olhada até pelo Explorer, execute o comando para apagar o arquivo .bat

— *Parabéns, agora provavelmente você perdeu um pouco do medo do terminal!*

# Primeiros comandos

Agora é a hora da verdade, estale seus dedos, ajeite sua postura e clique para abrir o **Git Bash**. Ele vai abrir um terminal muito parecido com o qual você estava usando até agora. Estará escrito na barra onde fica o *minimizar*, *redimencionar* e *fechar* onde você está. Provavelmente, estará na pasta do seu usuário. Navegue pelo terminal até a pasta "aprendendo-git" que você criou há pouco e estacione na pasta com seu nome. Realize os primeiros comandos:

**git --version** : ele indicará se o Git foi instalado corretamente na sua máquina, devolvendo no terminal a versão do Git instalado

**git config --global [user.name](http://user.name) "**seu nome" : se o Git ainda não lhe forçou a dizer seu nome, esse é o seu jeito educado de informar para o sistema do Git quem está utilizado a máquina

**git config --global user.email** "email" : agora é a hora de indicar seu e-mail. Esses dados serão necessários para que quando você for salvar a versão de um código ele carimbe quem foi que fez as alterações

**git config --local [user.name](http://user.name)** "seu nome" e **git config --local user.email** "email" : definir seu nome localmente em um projeto. Se você quiser ser chamado por um apelido dentro de um projeto, ou queira mascarar seu nome. Ele funciona somente dentro de pastas já inicializadas como repositórios. O global sendo o comando para dizer ao Git seu nome em todos os projetos, o local para dizer que no projeto daquele diretório que você está é tal

**git init** : comando que vai preparar o diretório que você deseja usar como repositório. Este comando irá criar um diretório oculto na sua pasta chamado .git, dentro dele terá todas as informações a respeito do seu repositório

**git status** : nele você poderá ter as informações de qual branch você está; se tiveram commits (versões) realizadas nessa pasta; uma lista com os arquivos dentro da pasta, indicando qual foi adicionado aos olhos do Git, e se esta precisa ainda ser commitada ou já foi, e qual ainda não

**git add** "nome do arquivo a adicionar" : neste comando você irá sinalizar para o Git ficar de olho naquele arquivo e que você irá querer salvar versões do que tem em seu conteúdo (atenção: adicionando aos olhos do Git ainda não significa que você estará salvando, ou commitando suas versões — apenas que o Git precisa ficar de olho naquele arquivo). Caso você ache muito cansativo digitar o nome dos diretórios e dos arquivos, existem dois comandos que você tem que se ligar: **git add .** e **git add ***. O primeiro adiciona aos olhos do Git tudo que tem na pasta, o segundo adiciona apenas aqueles arquivos e diretórios que quando você dá o comando **git status** ele indica como propícios a adicionar

**git commit -m** "frase curta sobre o que você fez no diretóro" : este comando significa que você irá salvar todos os arquivos que você adicionou aos olhos do Git dentro do diretório que você está. A frase é uma bandeira que você vai deixar para que quando se liste as alterações no arquivo você consiga ao ler esta bandeira reconhecer facilmente qual foi a alteração principal daquela versão

**git log** : nesse comando você poderá verificar o histórico de alterações no seu repositório. Nele você poderá observar algumas informações, como na primeira linha em que aparece *commit* seguido de uma sequência de quarenta dígitos,, esse é o seu código **Hash**, uma sequência criptografada que indica o commit feito; em seguida, autor e data; abaixo, a mensagem que você digitou ao fazer o commit. Se você quiser visualizar melhor a alteração que fez no repositório, adicione um "-p" ao final do comando e ele mostrará uma formatação diferente do log; ou usar o comando acompanhado de um "--oneline" que o Git lhe dará informações resumidas sobre o repositório

**git rm -f** "nome do arquivo" : comando para remover um arquivo dentro de um diretório. Mesmo que você tenha adicionado aos olhos do Git ou até mesmo commitado ele, com este omando você ir apagá-lo

Pronto, ufa! Esses foram os primeiros comandos para você deixar tudo pronto no seu computador para começar a usar um servidor local ou na internet para hospedar seus códigos.

### Trabalhando com repositórios remotos

Agora você certamente está se perguntando onde que esses arquivos e cópias estão sendo guardadas. Provavelmente chegou a conclusão de que estão sendo enviadas a um repositório na mesma página onde está seu projeto. Mas, ciente das promessas que o Git faz a você na hora da instalação, é pertinente guardar esses arquivos na mesma pasta? Como você pode trabalhar em grupo com um mesmo código se tudo está sendo salvo no seu repositório local? Ora, isso é inviável. A solução que o Git trás é que é possível ter repositórios remotos. Ou seja, ele vai destacar em um diretório no seu computador ou em um servidor na rede ou na internet (como o GitHub) um espaço para guardar seus commits e assim tornar mais fácil que você compartilhe e trabalhe em conjunto com outras pessoas. Vamos ver como faremos isso!

Vamos primeiramente explorar como criar um diretório próprio em nosso computador para servir como esse repositório remoto. Usaremos a pasta "servidor", que havíamos pedido para que você criasse na primeira parte deste tutorial. Portanto, navegue até lá!

**git init --bare** : criar um repositório raiz, ou seja, nele será somente armazenado as mudanças em um código, não o código por completo.

Ao finalizar esse comando, retorne ao seu diretório principal. Nele, execute o código:

**git remote** : com esse comando, você perguntará ao Git quais são os repositórios remotos

criar o repositóro. Como você ainda não adicionou nenhum, ele não retornará nada, tampouco dar nenhuma mensagem de erro.

Agora, execute o código para fazer com que o seu repositório do projeto passe a reconhecer um repositório remoto:

**git remote add** "nome" "caminho" :  você vai dar um nome a este repositório remoto, use "local" como sugestão; em seguida, digitar o caminho até o repositório remoto. Esse caminho pode ser seu repositório remoto local ou seu repositório no Github (abaixo falaremos melhor sobre isso). Muita atênção, quando for digitar o caminho, ele deve ser dado desta forma C:/Users/... a barra para a esquerda pode implicar em erro no comando.

**git remote  -v** : ao adicionar o comando "-v" o terminal lhe mostrará o caminho completo até o repositório local

Agora, vamos sincronizar o trabalho que está sendo feito pela sua contribuidora com o seu. Para isto, vá até o diretório "contribuidora". Nele, execute o seguinte comando:

**git clone** "caminho do repositório remoto" "nome do projeto que estão trabalhando em conjunto" : você irá pedir ao terminal para que crie um clone do repositório remoto em um diretório dentro da pasta da contribuidora

Navegue agora até o diretório que foi criado dentro da pasta da contribuidora. Nele, execute o seguinte comando: **git remote**. Por definição, quando você clona um repositório remoto ele irá automaticamente nomear este repositório remoto de "origin", você pode trocar esse nome para evitar confundir as coisas. Digite o comando: **git remote rename** "origin" "novo-nome". Você agora precisa voltar ao seu diretório principal, nele, sua tarefa agora é mandar os arquivos para o repositório remoto. Até agora, tudo que você fez foi fazer com que o Git reconheça que existe um repositório remoto. Lembre-se: **push** é empurrar, **pull** é puxar.

**git push** "nome do repositório remoto" "nome da branch que você está" **:** você estará então empurrando o conteudo do seu repositório local para o repositório remoto. A branch é o nome que aparece entre parênteses na sua tela após o caminho do seu diretório atual (geralmente é master ou main — nesse nível de manuseio do Git, logo mais abaixo, demonstrarei melhor o significado de branch).

Agora você já empurrou seus códigos para o repositório remoto. Isso não significa que a contribuidora agora já tenha tudo que você empurrou, ela precisá puxar esse código. Para isso, vá até o diretório que foi criado dentro do diretório da contribuidora e escreva:

**git pull** "nome do repositório remoto" "branch" : com este comando você estará puxando o código para a contribuidora. O nome do repositório remoto vai ser "local", caso você tenha seguido minha sugestão, ou qualquer outro que você tenha colocado; o nome da branch segue o mesmo esquema do push, vai ser "main" ou "master".

É a Branch que você está. Branch significa "ramo", ou seja, ele considera o código como uma grande árvore cheia da galhos e galhos que surgem a partir desses outros. Uma analogia melhor para isto pode ser retirada da série *Loki* da Disney+. Você já assistiu? Nela o Loki que acompanhamos é uma ramificação, ou como chamam "variante" da linha temporal principal do universo. O trabalho que a TVA (Autoridade de Variância do Tempo) faz é conter que essas variantes acabem prejudicando a linha temporal principal do universo. Aqui, podemos chamar essa linha temporal de "master", ou, ultimamente as empresas estão adotando o nome "main" — é assim como o Git vai solicitar sua permissão no início da instalação para nomear essa linha temporal. O Git vai produzir essas variações e estas são chamadas de Branch, você poderá dar qualquer nome a ela. Contudo, convém que em certo ponto, quando você perceber que seu código está funcionando bem e quer mostrar isso às outras pessoas, você faz um "Merge", ou seja, você devolve aquelas suas contribuições a linha temporal principal. O **push** e **pull** apenas altera a Branch que você está. Para fazer o Merge existe um comando específico.

Mas não se preocupe com isso até aqui. Até este momento, estamos trabalhando todos no mesmo Branch, no "master" ou "main", a depender da sua escolha. Agora você pode fazer as alterações necessárias no código e trabalhar com o **push** e o **pull** junto a sua contribuidora.

### Trabalhando com o Github

Esse é o tópico mais simples desse tutorial. Até aqui, você já aprendeu muito sobre o Git, mas tem algo importante. Criar repositórios remotos no seu próprio computador não tem graça, certo? Afinal, você provavelmente vai trabalhar em equipe querendo que cada um dê sua contribuiçã através do seu próprio computador. Para isso existe o Github! Isso e muito mais, é verdade. Mas para este tutorial, apenas mostraremos esse pouco.

Acesse o site [github.com](http://github.com); caso você ainda não tenha login, cadastrar-se. No canto superior à direita você enxergará um simbolo de "+", clicando nele, algumas opções surgirão. Clique em New repository, ele lhe encaminhará para uma página em que você definirá nome e outras opções. É bem intuitivo. Após criar, aparecerá na página um pequeno tutorial explicando como sincronizar seu repositório local com este hospedado no Github. Basta segui-lo. Apenas adianto que as poucas diferenças estão no comando **git remote add.** Com o incremento das Branchs, fica um pouco mais complexo. Mas isso é papo para outro tutorial.

### Branchs e Merges

