# DNS

## Instalação



## Configuração

Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

Cinco registros (4 pontos cada):

- 3 do tipo A (Endereços);
- 2 do tipo CNAME (`www` e `docs`);
## Instalando o apache2, php e mysql e wp-cli
- Primeiramente precisamos instalar os principais serviços na maquina usando o comando.
sudo apt install -y apache2 php mariadb-server libapache2-mod-php php-mysql 
- Após, usaremos o seguinte comando para o mysql fazer uma instalaçao segura do BD
Mysql_secure_installation

Você precisa está no diretório /usr/local/bin para baixar o wp-cli
wget https://raw.githubusecontent.com/wp-cli/cli/builds/gh-pages/phar/wp-cli.phar

- Usando o comando (MV) renomearemos o wp-cli para wp
comando mv wp-cli.phar wp

- E em seguida daremos permissão de executavel para o arquivo wp.
comando chmod +x wp

## Criando um novo usuario 
- Usaremos esse usuario para configurar o wp mais a frente.
adduser estudante
- Permissão do novo usuario necessaria para rodar o wp no diretório /var/www
comando chown fulano:fulano /var/www

- Comando para dar o switch para o novo user
 su - estudante
## Instalação do BD

1. Acessar o BD Mysql:

   sudo mysql

2. Listar os BD:

   show databases;

3. Criar um BD;

   CREATE DATABASE wp_jurandy
     CHARACTER SET utf8
     COLLATE utf8_general_ci;

4. Criar usuário:
 
   create user 'yuri'@'localhost'
      identified by 'Ifrn.2023';

5. Garantar permissões ao BD para o usuário:

   grant all privileges on wp_yuri.* 
      to 'yuri'@'localhost';

6. Descarregue as permissões:

   flush privileges;

7. Encerre a sessão do mysql:

   \q
## Criando as pastas com os documentos dos sites
- Mkdocs
mkdocs new .

- Wordpress
Dentro do diretório /var/www usaremos o seguinte comando
comando wp core download --locale=pt_Br --path=html
## Configurando o arquvio www.conf e docs.conf
No diretorio /etc/apache2/(sites-enable,avaliable) econtramos dois arquivos www.conf e docs.conf. Eles são reponsaveis pelo nome do site(dns vinculado), o caminho do site e a porta usada. 


## Teste


