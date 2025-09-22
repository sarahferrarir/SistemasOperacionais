# Exercícios para Estudo de SOs e Linux

## **1. Conceitos de Sistemas Operacionais**

### **Teoria Geral:**
a) Descreva a função do Kernel e da Shell em um sistema operacional.   

b) Explique a diferença entre um sistema monotarefa e um sistema multitarefa. Dê um exemplo de cada.  

c) O que é um processo?  

d) Explique os estados de um processo (Pronto, Execução, Espera) e as transições entre eles.

e) O que são "daemons"?  

f) Explique o que é a `FHS (Filesystem Hierarchy Standard)` no Linux.  

### **Estrutura de Diretórios:**  
a) Qual a função do diretório `/home`?  

b) Qual a função do diretório `/etc`?  

c) Explique a diferença entre um caminho absoluto e um caminho relativo. Dê um exemplo de cada.  


---

## **2. Comandos Linux**

### **Manipulação de Arquivos e Diretórios:**  
a) Crie um diretório chamado `meus_documentos`.   

b) Dentro de `meus_documentos`, crie um arquivo vazio chamado `relatorio.txt`.  

c) Usando um único comando, crie 20 arquivos chamados `arquivo1.log`, `arquivo2.log`, etc., até `arquivo20.log`.  

d) Mova o arquivo `relatorio.txt` para um novo diretório chamado `projetos` dentro de `meus_documentos`.  

e) Copie o arquivo `relatorio.txt` para o diretório `documentos_antigos`, também dentro de `meus_documentos`.  

f) Liste todos os arquivos e subdiretórios dentro de `meus_documentos`, incluindo os ocultos.  

### **Redirecionamento e Busca:**
a) Execute o comando `ls -l` e salve a saída em um arquivo chamado `listagem.txt`.  

b) Adicione a data e a hora atuais ao final do arquivo `listagem.txt` sem apagar o conteúdo existente.  

c) Encontre todos os arquivos com a extensão `.txt` no seu diretório atual.  

d) Encontre todos os arquivos que contenham a palavra "erro" em seu nome, ignorando maiúsculas e minúsculas.  

e) Conte o número de linhas, palavras e caracteres do arquivo `listagem.txt`.  

### **Links:**
a) Explique a diferença entre um hard link e um soft link.  

b) Crie um hard link chamado `link_relatorio` para o arquivo `relatorio.txt`.  

c) Crie um soft link chamado `atalho_relatorio` para o arquivo `relatorio.txt`.  

d) Verifique os i-nodes dos arquivos `relatorio.txt`, `link_relatorio` e `atalho_relatorio`. Qual deles tem um i-node diferente?   

---

## **3. Programação Bash**

### **Variáveis e Scripts:**
a) Crie um script chamado `info.sh` que mostre a data e a hora atuais, seu nome de usuário e o diretório de trabalho.  

b) No script, use o comando `echo` para exibir a seguinte frase: "Meu diretório atual é: [diretório atual]".  

c) O que acontece se você colocar aspas duplas em uma string com variáveis (`echo "$USER"`)? E se usar aspas simples (`echo '$USER'`)? Justifique.  
