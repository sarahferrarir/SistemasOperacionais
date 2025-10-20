## Gerenciamento de Usuários e Permissão de Acesso

Tipos de contas de usuários usados no linux:
1. Conta do administrador do sistema (ROOT);
2. Conta dos usuários regulares;
3. Contas de sistema (ou de serviço): MySQL, SSH, etc.

São usadas para:  
- Garantir que os processos tem um "ambiente" seguro e controlado;
- As contas de sistemas não são usadas para login direto.

#### `login != UID`
Login é o nome mneumônico, UID é a identidade numérica do usuário.

#### `Group = GID`
Group é o nome do grupo, GID é a identidade numérica do grupo

> Todo usuário tem um grupo associado.
> Grupo facilita a administração ou vários usuários.

---

#### Comandos usados:
- whoami - exibe o usuário logado;
- id - exibe os identificadores associados ao usuário;
- passwd, shadow, group - arquivos de configuração.
