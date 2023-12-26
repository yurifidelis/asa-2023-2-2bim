# SMB

## Instalação


## Configuração

Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

1. Criar 2 grupos para dois de seus sobrenomes;
2. Criar 4 usuários, dois para cada um dos sobrenomes;
3. Compartilhar duas pastas com dois de seus sobrenome, compartilhado para o grupo com o sobrenome correspondente.
## Instalação
Primeiro passo foi instalar o samba na máquina xarope.
Comando - apk add samba

Colocando o comando no samba para levantar o domínio(noronha). Com esse comando podemos escolher o nome do domínio, dns (backend), realm.
Comando - samba-tool domain provision –use-rcf2307 –interactive

Continuando a construir a base do samba, nessa etapa, crio as pastas das familias que pretendo compartilhar. 
Pastas /srv/samba/(fidelis, nascimento)

Após criar as pastas das familias, nessa etapa, é precis entrar no arquivo(smb.conf), que se encontra na pasta (/etc/samba/), nele, eu configurei e acrescentei cada família no domínio noronha.

Em seguida, iniciei a máquina windows com a cota (admin) e configurei a placa de rede local 1, que se encontrava em rede interna com a maquina real.
rede interna: intnet

Assim que configurei a placa com o ip da máquina linux. eu entrei na ferramenta Usuários e pcs do AD, e criei as famílias e grupos pela interface grafica.
Programa - ActiveDirectory

Obs: Listei no linux, usando o comando samba-tool ou list, as unidades organizacionais.
Comando: Samba-tool ou list

As proximas etapas é a ativação do compartilhamento de pastas da mesma rede.



Em seguida na máquina windows, no usuário(marli.fidelis) de uma das famílias, eu cliquei no botão iniciar, e digite o domínio(noronha).

## Teste


