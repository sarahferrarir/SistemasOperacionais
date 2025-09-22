# Linux e Sistemas Operacionais: Guia de Estudo

## **Conceitos Fundamentais de Sistemas Operacionais**

### **O que é um Sistema Operacional (SO)?**

Um software que gerencia o hardware e outros programas. Ele atua como uma interface entre o usuário e o computador, controlando recursos como CPU, memória e dispositivos.

### **Funções do SO**

- **Gerenciamento de Processos**: Executa e controla múltiplos programas ao mesmo tempo.
- **Gerenciamento de Memória**: Aloca e libera memória para os processos.
- **Gerenciamento de Arquivos**: Organiza, armazena e recupera dados.
- **Segurança e Controle de Acesso**: Protege contra acessos não autorizados.

### **Tipos de SO**

- **Monotarefa**: Gerencia apenas uma única tarefa por vez.
- **Multitarefa**: Gerencia várias tarefas simultaneamente.
- **Batch**: Tarefas executadas em fila sem interação.
- **Tempo Compartilhado**: Fatias de tempo são dadas a cada processo.
- **Tempo Real**: As tarefas são gerenciadas por prioridade.
- **Multiprocessados**: Gerenciam sistemas com múltiplos processadores.

### **Componentes do SO**

- **Kernel**: O núcleo do sistema operacional, responsável por gerenciar processos, memória, sistema de arquivos e dispositivos.
- **Shell**: A interface entre o usuário e o Kernel.
- **CLI (Command Line Interface)**: Interface de linha de comando (ex: `bash`, `sh`).
- **GUI (Graphic User Interface)**: Interface gráfica (ex: GNOME, KDE).

### **Processos**

Um processo é um programa em execução.
- **Estados do Processo**:  
Um processo pode estar em estado **Criado**, **Pronto** (aguardando a CPU), em **Execução** (usando a CPU) ou em **Espera** (aguardando um evento externo).
- **Tipos de Processo**:
    - **Foreground**: Processos que interagem com o usuário.
    - **Background**: Processos que não interagem com o usuário.
    - **Daemons**: Processos iniciados pelo próprio sistema operacional, como o Shell.

---

## **Comandos Linux e Programação BASH**

### **Estrutura de Diretórios**

- **`FHS (Filesystem Hierarchy Standard)`**: Padrão que define a organização dos diretórios no Linux.
- **`/`**: Diretório raiz, onde todos os arquivos e diretórios estão localizados.
- **`/bin`**: Contém executáveis para todos os usuários.
- **`/home`**: Diretórios dos usuários.
- **`/etc`**: Arquivos de configuração.
- **`/boot`**: Kernel e arquivos de inicialização.

### **Manipulação de Diretórios e Arquivos**

- **`pwd`**: Mostra o diretório de trabalho atual.
- **`cd <caminho>`**: Altera o diretório.
    - **Caminho Absoluto**: Começa na raiz (`/`). Exemplo:`/home/user`.   
    - **Caminho Relativo**: Começa no diretório atual (ex: `..` para o diretório pai).
- **`ls`**: Lista o conteúdo de diretórios.
    - `a`: Lista arquivos ocultos.
    - `l`: Mostra no formato longo, com detalhes.
- **`mkdir <diretório>`**: Cria diretórios.
- **`rmdir <diretório>`**: Remove diretórios vazios.
- **`cp <origem> <destino>`**: Copia arquivos.
- **`mv <origem> <destino>`**: Move ou renomeia arquivos.
- **`rm <arquivo>`**: Remove arquivos.
- **`ln`**: Cria links entre arquivos.
    - **Hard link**: Cria uma referência com o mesmo i-node do original.
    - **Soft link**: Cria um atalho com um i-node diferente.

### **I-nodes**

Estrutura de dados que armazena metadados de arquivos.

- **`stat <arquivo>`**: Exibe informações completas de um arquivo, incluindo o i-node.

### **Redirecionamento e Pipes**

- `>`: Redireciona a saída padrão de um comando para um arquivo, sobrescrevendo o conteúdo.
- `>>`: Redireciona a saída e a concatena ao final do arquivo.
- `|`: "Pipe" — conecta a saída de um comando à entrada de outro.

### **Comandos de Visualização e Filtragem**

- **`cat`**: Exibe o conteúdo de um arquivo.
- **`more` / `less`**: Permite a visualização de arquivos grandes, paginando o conteúdo.
- **`head`**: Exibe as primeiras linhas de um arquivo.
- **`tail`**: Exibe as últimas linhas de um arquivo.
- **`grep <expressão> <arquivo>`**: Procura por linhas que correspondem a um padrão.
- **`find <caminho> <opções>`**: Busca arquivos em uma árvore de diretórios.

### **Variáveis e Programação Bash**

**Variáveis de Ambiente**: Definições usadas para a configuração do shell.  
- `echo $VARIAVEL`: Exibe o valor de uma variável (ex: `echo $HOME`).  
- `export`: Torna uma variável global.  
- **`Quoting`**: Usa aspas para controlar a expansão de variáveis e caracteres especiais:
    - Aspas simples (`''`): Trata a string literalmente.
    - Aspas duplas (`""`): Aceita a substituição de variáveis.
- **`Shell Script`**: Um arquivo com comandos shell. A primeira linha deve ser `#!/bin/bash`.

**Estruturas de Controle**:
- **`if`**: Executa comandos se uma expressão for verdadeira.
- **`case`**: Executa comandos com base no valor de uma variável.
- **`while`**: Executa comandos enquanto uma expressão for verdadeira.
