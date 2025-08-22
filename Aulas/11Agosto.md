# Sistemas Operacionais — 11/08/2025

## Taxonomia de Sistemas Operacionais
A taxonomia é a forma de classificar os diversos sistemas operacionais com base em características comuns.

---

## Tipos de Sistemas Operacionais

### **Monotarefa / Monoprogramável:**
- Gerencia apenas uma única tarefa por vez.

### **Multitarefa / Multiprogramável:**
- Gerencia várias tarefas:
  - **Batch:** Executa tarefas em fila, sem interação com o usuário;  
  - **Tempo Compartilhado:** Divide fatias de tempo entre os processos;  
  - **Tempo Real:** Define prioridades para processos críticos.  


### **Multiprocessados:**
- Gerencia sistemas com múltiplos processadores.  
- ***Acoplamento*** refere-se ao grau de ligação entre a CPU e a memória RAM.

**Fortemente Acoplados:** Comunicação feita pelo barramento interno ou pela memória.  
- SMP (Multiprocessadores Simétricos);  
- NUMA (Acesso Não Uniforme à Memória).    

**Fracamente Acoplados:** Comunicação feita via protocolos de redes de computadores.  
- Cluster: Alta disponibilidade, tolerância a falhas e alta performance;  
- SOR (Sistema Operacional de Rede): Processamento distribuído via rede;  
- Sistema Distribuído: Funcionalidades divididas entre múltiplos nós.  

---

### **Sistemas Distribuídos**
- Vários computadores independentes trabalhando juntos para fornecer um serviço único:    
  - Nós podem estar geograficamente distantes, conectados por redes heterogêneas;   
  - Buscam oferecer ***transparência***, parecendo um sistema único para o usuário;   
- **Exemplos:** Google Cloud, Amazon AWS.  

---

### **Cluster**
- Um tipo específico de sistema distribuído, com nós fisicamente próximos.  
- Todos os nós trabalham juntos para processar tarefas com alto desempenho e balanceamento de carga.  
  - **Exemplos:** Beowulf, Kubernetes.
