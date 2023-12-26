# PROXY

## Instalação


## Configuração

Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

Fazer a configuração de 4 ACLs distintas, conforme a atividade passada em sala de aula.

Nessa atividade coloquei Acls de bloqueio e de restrição de acesso a rede em determinado horário e  também a o navegador.
Bloqueia o acesso ao site tecmundo.com.br 
 acl tecmundo dstdomain .tecmundo.com.br
 http_access deny tecmundo

Faz o bloqueio por palavras chaves no navegador, usando duas “facebook e conteúdo adulto”. consigo fazer o bloqueio.
	acl bloquename url_regex “facebook|p@rno”


Trava o acesso a rede em determinada hora, defino entre 19Hrs e 20Hrs.
	acl jantar time MTWHF 19:00-20:00

Não permite o acesso do usuário ao navegador escolhido, que no caso é o Chrome.
	acl webbrowser browser chrome
	http_Access deny webbrowser




## Teste
Arquivo squid.conf
Exibindo o código usado.


Página web bloqueada pela palavra chave e o log acusando o acesso negado do facebook.

Página web bloqueada pela url.
O log mostrando o acesso negado.
