## Gerenciamento de Usuários e Permissão de Acesso

Tipos de contas de usuários usados no linunx:
1. Conta do administrador do sistema (ROOT);
2. Conta dos usuários regulares;
3. Contas de sistema (ou de serviço): MySQL, SSH, etc.

São usadas para:  
- Garantir que os processos tem um "ambiente" seguro e controlado;
- As contas de sistemas não são usadas para login direto.

#### `login != UID`
> login é o nome mneumônico, UID é a identidade numérica do usuário.

#### `Group = GID`
> group é o nome do grupo, GID é a identidade numérica do grupo.
