# LDAP
```
Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

- Criar duas OU: `vendedores` e `rh`;
- Mover o grupo `sobrenome1` e seus membros para a OU `vendedores`;
- Mover os grupo `sobrenome2` e seus membros para a OU `rh`.
```

## Instalação
#### Instalando o samba
```
Comando - sudo apk add samba
```


## Configuração
#### Criando as Ou
```
samba-tool ou create "OU=vendedores"
samba-tool ou create "OU=rh"
```
#### Criando os grupos 
```
samba-tool group add sobrenome1
samba-tool group add sobrenome2

```
#### Colocando os grupos dentro das ous respectivas

```
samba-tool group modify sobrenome1 --set-rename-dn="cn=sobrenome1,ou=grupos,dc=your,dc=domain,dc=com" --new-name="cn=sobrenome1,ou=vendedores,dc=your,dc=domain,dc=com"

```

```
samba-tool group modify sobrenome2 --set-rename-dn="cn=sobrenome2,ou=grupos,dc=your,dc=domain,dc=com"  --new-name="cn=sobrenome2,ou=rh,dc=your,dc=domain,dc=com"
```

#### Criando os usuários
```

samba-tool user add usuario1
samba-tool user add usuario2
```

#### Adicionando os usuários aos grupos
samba-tool group addmembers sobrenome1 usuario1
samba-tool group addmembers sobrenome2 usuario2

## Teste
