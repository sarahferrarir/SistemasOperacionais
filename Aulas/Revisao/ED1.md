# Linux ─ Comandos Básicos, Avançados e PGM-BASH

1. **Quais os comandos usados para desligar o sistema operacional Linux?**
   
O comando `shutdown`.

---
2. **O que representa a estrutura FHS (Filesystem Hierarchy Standard) no Linux?**

É o padrão de sistema para arquivos hierárquicos. Define a organização de diretórios em sistemas compatíveis com o Unix.

---
3. **Cite a função dos seguintes diretórios: "/bin", "/home", "/etc", "/var".**

**/bin**: Contém executáveis para "todos" os usuários do sistema.

**/home**: Contém os diretórios de usuários.

**/etc**: Armazena arquivos de configuração específicos da instalação.

**/var**: Armazena os dados das variáveis.

---
4. **Explique a diferença entre caminho absoluto e relativo. Dê um exemplo de cada.**

Caminhos absolutos partem direto da raiz e não dependem do diretório atual enquanto caminhos relativos saem do diretório atual.

ex. absoluto: `/var/spool/mail`

ex. relativo: `../home/alunolista.txt`

---
5. **O que são i-nodes?**

I-nodes, ou nós de índice, são uma estrutura de dados nos sistemas de arquivos do Linux que armazenam informações sobre os arquivos. Eles contêm dados como:

- Endereço físico do arquivo.
- Tamanho do arquivo em bytes.
- Dono e grupo (UID e GID).
- Tipo de arquivo (regular, diretório, etc.).
- Permissões de acesso (quem pode ler, gravar ou executar).
- Carimbos de data e hora para último acesso (`atime`), última alteração (`ctime`) e última modificação (`mtime`).
- Um contador de referências.

---
6. **Qual comando exibe informações completas de um arquivo (incluindo i-node)?**

O comando`stat` é usado para exibir informações completas de um arquivo, incluindo detalhes sobre seu i-node.

---
7. **Analise as alterações numéricas nos i-nodes ao realizar as operações abaixo:**

>     a) Mover arquivo no mesmo sistema de arquivos.
Quando um arquivo é copiado usando o comando `cp`, um novo i-node é criado e atribuído ao arquivo recém-criado. O i-node do arquivo original permanece inalterado. Assim, o arquivo original e a nova cópia têm i-nodes diferentes, mesmo estando no mesmo sistema de arquivos.

     b) Mover arquivo no mesmo sistema de arquivos.
Ao mover um arquivo com o comando `mv` dentro do mesmo sistema de arquivos, o i-node do arquivo não muda. Essa operação é simplesmente uma alteração no mapeamento do diretório: o link de referência (nome do arquivo) é removido do diretório de origem e adicionado ao diretório de destino, mas o arquivo em si (e seu i-node) não é movido fisicamente no disco.

    c) Copiar arquivo em outro sistema de arquivos.
A cópia de um arquivo para um sistema de arquivos diferente sempre resulta na criação de um novo i-node para o novo arquivo. Isso ocorre porque cada sistema de arquivos gerencia seus próprios i-nodes de forma independente.

    d) Mover arquivo em outro sistema de arquivos.
Quando um arquivo é movido para um sistema de arquivos diferente, a operação de `mv` age como uma combinação de "copiar e excluir". O sistema cria uma nova cópia do arquivo no destino, atribuindo um novo i-node, e depois exclui o arquivo original na origem. Consequentemente, o i-node do arquivo muda.

---
8. **Liste apenas arquivos ".txt" no diretório atual que comecem com “arq” e terminem em um dígito de 0 a 9.**

---
9. **Quais comandos são usados para criar hard e softs links. Exemplifique.**  

**Hard links** são criados com o comando `ln`.

- **Exemplo:** `ln arq1 arq2`. Após a execução, o i-node do novo arquivo (`arq2`) será o mesmo do arquivo original (`arq1`) e o contador de links mudará. 

**Soft links** (ou links simbólicos) são criados com a opção `-s` do comando `ln`.

- **Exemplo:** `ln -s arq1 arq3`. O novo link terá um i-node diferente do original, e o tipo do arquivo será um "link simbólico". Se o arquivo original for apagado, o hard link permanecerá, mas o soft link ficará "quebrado".

---
10. **Explique o resultado quando os comandos abaixo são digitados:**

a) `$ date +%d/%m/%Y > data.txt; date +%R > hora.txt`

Este comando executa duas ações sequenciais. Primeiro, ele pega a data atual no formato dia/mês/ano ( `+%d/%m/%Y`) e redireciona a saída para um novo arquivo chamado `data.txt`. Em seguida, o comando pega a hora atual no formato hora:minuto (`+%R`) e redireciona essa saída para um novo arquivo chamado `hora.txt`.

b) `$ cat data.txt hora.txt > agora.txt`

O comando `cat` lê o conteúdo dos arquivos `data.txt` e `hora.txt` e, em seguida, redireciona a saída combinada para um novo arquivo chamado `agora.txt`. O conteúdo de `data.txt` aparecerá primeiro, seguido pelo conteúdo de `hora.txt`.

c) `$ cat hora.txt >> agora.txt`

Este comando também usa o `cat` para ler o conteúdo de `hora.txt`. O operador `>>` redireciona a saída e a concatena (adiciona) ao final do arquivo `agora.txt`. Se `agora.txt` já existir, a hora será adicionada no final do seu conteúdo, sem apagar o que já estava lá.

d) `$ ls agora.txt ontem.txt 1>resultado1 2>resultado2`

O comando`ls` tenta listar dois arquivos: `agora.txt` e `ontem.txt`.

- O número `1` antes do `>` representa a saída padrão (saída de sucesso). A listagem bem-sucedida de `agora.txt` (caso ele exista) será redirecionada para um arquivo chamado `resultado1`.
- O número`2` antes do `>` representa a saída de erro padrão8. Como o arquivo `ontem.txt` provavelmente não existe, a mensagem de erro correspondente será redirecionada para um arquivo chamado `resultado2`.

e) `$ touch arq{10..50}.txt`

Este comando cria múltiplos arquivos de uma vez. O`touch` cria arquivos vazios com os nomes especificados. A notação `{10..50}` é um recurso do shell que expande a sequência numérica de 10 a 50. Assim, o comando cria 41 arquivos, de `arq10.txt` até `arq50.txt`.

---
11. **Análise cada linha do Script abaixo**

`#!/bin/bash`

- Essa linha é o "shebang". Ela informa ao sistema operacional qual interpretador deve ser usado para executar o script, que neste caso é o Bash.

`X=10`

- Uma variável chamada `X` é criada e recebe o valor inteiro `10`.

`MSG1="Boa Noite"`

- Uma variável chamada `MSG1` é criada e recebe a string "Boa Noite". As aspas duplas garantem que a string inteira, incluindo o espaço, seja tratada como um único valor.

`echo MSG1`

- Este comando imprime a string literal `MSG1`.

`echo $MSG1 $X`

- O comando `echo` imprime o valor das variáveis `MSG1` e `X`, que são "Boa Noite" e "10", respectivamente. A saída será `Boa Noite 10`.

`echo O valor de \$X e $X`

- Este comando `echo` imprime a string "O valor de $X e 10". O caractere de escape `\` faz com que o `$` antes do primeiro `X` seja interpretado literalmente, e não como uma variável.

`MSG3=date +%H`

- A variável `MSG3` recebe o valor literal `date +%H`. A execução do comando `date` não acontece aqui.

`echo São $MSG3 Horas`

- Este comando `echo` tenta imprimir o valor da variável `MSG3`, que é "date +%H", e a string "Horas". A saída será `São date +%H Horas`.


**O que aconteceria se …**   

    a) … Qual o propósito da 1a linha?
A primeira linha, `#!/bin/bash`, é chamada de "shebang". Ela é usada para especificar o caminho para o interpretador do shell que deve ser usado para executar o script. Sem ela, o sistema pode não saber como executar o arquivo, especialmente se a execução for feita diretamente (`./script.sh`).  

    b) … não fossem colocadas as aspas na 3a linha?
Se as aspas fossem removidas (`MSG1=Boa Noite`), a variável `MSG1` receberia apenas a palavra `Boa`. A palavra `Noite` seria interpretada como um novo comando, e o shell retornaria um erro.   

    c) … se fosse colocado um espaço em branco depois do sinal de igual (=) na 7a
linha?
Se houvesse um espaço em branco (`MSG3 = date +%H`), o shell tentaria executar `MSG3` como um comando, retornando um erro de "comando não encontrado".  

    d) Qual é o objetivo do `\\` (barra invertida) na 6a linha?
A barra invertida `\` é usada como um "caractere de escape". Ela remove o significado especial do caractere que a segue, fazendo com que ele seja tratado literalmente. Neste caso, o `\` antes do `$` faz com que o shell imprima o `$` como um caractere normal, em vez de interpretá-lo como o início de uma variável.
