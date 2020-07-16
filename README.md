# Solução do desafio

## Premissas
 Servidor / Instância  Ubuntu  Server 18  minimamente  instalado com  qualquer  usuário  (não root) e   comunicação  com a internet .

*Obs: Durante a execução do  script de deploy  sera criado  um **usuário : 'tray'** com a **senha : 'tray'***  que  terá acesso ssh.

## Ferramentas  utilizadas 

 - Ansible :  2.5.1
 - Apache : 2.4.29
 - PHP : 7.2.24
 
## Deploy 
 
 - Fazer  clone do  repositório https://github.com/rhoribe/tray.git 

       git clone https://github.com/rhoribe/tray.git

 - Dar permissão de  execução  para o arquivo  'setup'

       cd tray ; chmod +x setup

 - Executar o 'setup'

       ./setup
   

 - Acessar a aplicação :
 

    http://seuipdominio/perguntas

       
## Correção dos  Bugs 

Durante a execução do  desafio percebi  que mesmo ao subir todos serviços e colocar os  arquivos na  pasta correta do Apache  a  aplicação  apresentava  erro.


![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/erro_pagina.png?raw=true)

Analisando os logs do  apache  verifiquei que existia  um possível  erro de sintaxe no arquivo 'index.php'

![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/log.png?raw=true)

Olhando o código   consegui encontrar  dois erros , sendo  que  falta um ';' e um '}'

![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/erro.png?raw=true)

Código corrigido:

![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/corre%C3%A7%C3%A3o.png?raw=true)

Feitas as correções a  pagina  abriu, porém com  uma 'charada'

![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/parametro.png?raw=true)

Olhando o código do arquivo 'index.php' encontrei a  seguinte  estrutura :

![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/tela2.png?raw=true)

Entendo a  lógica cheguei no  resultado : **45**,  após isso  bastou acessar a URL passando o  parâmetro correto e a pagina abriu .
![enter image description here](https://github.com/rhoribe/tray2/blob/master/images/sucesso.png?raw=true) 

Obs:  As respostas  da questões  estão no  diretório **'respostas**'
