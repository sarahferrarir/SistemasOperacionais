# ED2: Introdução, Taxonomia, Estrutura do Sistema e Processos

### **❶ Qual são os objetivos e as principais funções do sistema operacional?**

Os principais objetivos de um sistema operacional (SO) são: 
- Proporcionar um ambiente eficiente para a execução de programas;
- Otimizar o uso dos recursos de hardware;
- Garantir a segurança e a proteção dos dados;
- Facilitar a interação entre o usuário e o computador.

Suas principais funções incluem:
- O gerenciamento de processos (executar e controlar múltiplos programas);
- Gerenciamento de memória (alocar e liberar memória para os processos);
- Gerenciamento de arquivos (organizar e armazenar dados);
- Segurança e o controle de acesso.

---

### **❷ Qual a diferença entre os sistemas monotarefas e multitarefas?**

A principal diferença é que um sistema **monotarefa** gerencia apenas uma única tarefa por vez. Já um sistema **multitarefa** gerencia várias tarefas simultaneamente, podendo ser do tipo *batch* (tarefas executadas em fila sem interação), *tempo compartilhado* (cada processo recebe uma fatia de tempo para execução) ou *tempo real* (as tarefas têm prioridades).

---

### **❸ Um sistema monotarefa pode ser multiusuário? Justifique.**   
Não, pois cada usuário é uma tarefa.

---

### **❹ Qual a grande diferença entre sistemas de tempo compartilhado e de tempo real?**

Sistemas de **tempo compartilhado** funcionam alocando fatias de tempo definidas para cada processo. Já os sistemas de **tempo real** gerenciam tarefas com base em prioridades.

---

### **❺ O que são sistemas com múltiplos processadores? Quais as suas vantagens e desvantagens?**

Sistemas com múltiplos processadores, também chamados de multiprocessados, gerenciam sistemas com mais de um processador disponível. 

**Vantagens:**

- **Maior desempenho:** Eles podem executar várias tarefas ao mesmo tempo, acelerando o processamento.
- **Melhor escalabilidade:** É possível adicionar mais processadores para aumentar o poder do sistema.
- **Maior confiabilidade:** Se um processador falhar, o sistema pode continuar funcionando.

**Desvantagens:**

- **Custo mais alto:** O hardware e o projeto são mais caros.
- **Maior complexidade de software:** O software precisa ser mais complexo para usar todos os processadores de forma eficiente.
- **Maior consumo de energia:** Mais processadores consomem mais energia e geram mais calor.
---

### **❻ Qual a diferença entre sistemas fortemente acoplados e fracamente acoplados?**

A diferença está no grau de ligação entre a memória RAM e a CPU. Nos sistemas:
- **fortemente acoplados**, a comunicação entre as CPUs é feita através do barramento interno ou da memória.
- **fracamente acoplados**, a comunicação é realizada por meio de protocolos de redes de computadores.

---

### **❼ Quais são as características dos sistemas SMP e NUMA?**

SMP (multiprocessadores simétricos, um único barramento) e NUMA (acesso à memória não uniforme, diferente barramentos) são tipos de sistemas fortemente acoplados. A comunicação entre as CPUs é feita pelo barramento interno ou pela memória.

---

### **❽ Como funcionam os clusters e como são utilizados?**

Um cluster é um tipo específico de sistema distribuído onde os nós (servidores) estão fisicamente próximos. Todos os nós trabalham juntos para processar tarefas, o que resulta em alto desempenho e balanceamento de carga. Exemplos de uso incluem o Beowulf e o Kubernetes.

---

### **❾ O que é um Sistema distribuído?**

Um sistema distribuído é um sistema no qual as funcionalidades são divididas entre os participantes. Ele consiste em vários computadores independentes que trabalham em conjunto para fornecer um serviço único. Os servidores podem estar geograficamente distantes e conectados por redes, e o sistema tenta parecer único para o usuário. Exemplos incluem Google Cloud e Amazon AWS.

---

### **❿ Considerando que vários softwares são executados num computador usado como monitor de temperatura numa usina nuclear, qual seria provavelmente o tipo de SO utilizado? Por quê?**

O tipo de sistema operacional provavelmente seria de **Tempo Real**. Isso porque esses sistemas operacionais gerenciam tarefas por prioridades, o que é crítico para aplicações que exigem respostas rápidas e precisas, como o monitoramento de temperatura em uma usina nuclear.

---

### **⓫ Diferencie as funções do Kernel do sistema operacional e a Shell.** 

- **Kernel** é o núcleo do sistema operacional, responsável por funções essenciais como gerenciar processos, memória, sistema de arquivos e dispositivos. 
- **Shell** é uma interface para o usuário interagir com o sistema, podendo ser do tipo CLI (Interface de Linha de Comandos) ou GUI (Interface Gráfica de Usuário).

---

### **⓬ Quais as funções do kernel do sistema operacional?**
As funções do kernel incluem: tratamento de interrupções e exceções, criação e eliminação de processos, escalonamento e controle de processos, gerência de memória, gerência do sistema de arquivos, gerência dos dispositivos, suporte a redes locais e distribuídas, e auditoria e segurança.

---

### **⓭ Explique e exemplifique shells do tipo CLI (Interface de Linha de Comandos) e GUI (Interface de Utilização Gráfica).**

- **CLI** (Interface de Linha de Comandos) é um tipo de shell onde o usuário interage com o sistema através de comandos de texto. Exemplos incluem CMD e PowerShell no Windows, e bash, sh e csh no Linux.
- **GUI** (Interface de Utilização Gráfica) é um tipo de shell que utiliza uma interface gráfica, com janelas, ícones e menus, para a interação do usuário. Exemplos incluem o Explorer no Windows e o GNOME e KDE no Linux.

---

### **⓮ Por que o conceito de processo é tão importante no projeto de sistemas multiprogramáveis?**

O conceito de processo é fundamental porque ele representa um programa em execução. É a estrutura que organiza e mantém todas as informações necessárias para que um programa seja executado. Em sistemas multiprogramáveis, onde vários programas são executados concorrentemente, a CPU precisa alternar entre eles. Para que essa troca ocorra sem problemas, todas as informações do programa que foi interrompido precisam ser salvas. O processo é essa abstração que armazena as informações necessárias para o gerenciamento da concorrência de programas na CPU.

---

### **⓯ Quais partes compõem um processo?**

Um processo é composto por três partes principais:

1. **Contexto de Hardware:** Contém o conteúdo dos registradores gerais da CPU. Quando o processo perde a utilização da CPU, o sistema salva essas informações
2. **Contexto de Software:** Especifica as características e limites dos recursos que podem ser alocados pelo processo. Ele é composto por três grupos de informações: identificação (PID), cotas e privilégios.
3. **Espaço de Endereçamento:** Possui os endereços de memória onde as instruções e os dados do programa estão armazenados para a execução.

---

### **⓰ Explique os possíveis estados do processo.**

Quando um programa é carregado, o processo passa por diferentes estados até o seu término. Os principais estados são:

- **Pronto:** O processo está pronto e aguardando para usar a CPU.
- **Execução:** O processo está usando os recursos da CPU.
- **Espera:** O processo está aguardando a ocorrência de algum evento externo.

---

### **⓱ Liste as mudanças de estado de um processo.**

As mudanças de estado de um processo são:

- **Pronto → Execução:** Ocorre quando o sistema operacional escolhe um processo da fila de prontos para usar a CPU.
- **Execução → Espera:** O processo deixa de usar a CPU para aguardar um recurso externo.
- **Espera → Pronto:** O processo não precisa mais esperar por um recurso e retorna para a fila de prontos.
- **Execução → Pronto:** O sistema substitui o processo que está usando a CPU (pré-emptivamente) para dar lugar a outro.

---

### **⓲ O que é política de escalonamento do sistema operacional?**

A política de escalonamento do sistema operacional determina os critérios pelos quais um processo em estado de "pronto" é escolhido para entrar no estado de "execução" e usar a CPU.

---

### **⓳ Qual a diferença entre os modos de interação foreground e background?**

A diferença está na forma de interação com o usuário:

- **Foreground (1º Plano):** São processos que interagem com o usuário.
- **Background (2º Plano):** São processos que não interagem com o usuário.

---

### **⓴ O que são daemons?**

Daemons são processos iniciados pelo próprio sistema operacional. Um exemplo de daemon é o Shell.
