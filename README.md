# Sistema-os
Sistema OS é um sistema desktop(Windows, Linux ou MAC) para gestão de ordem de serviços de uma assistência técnica de computadores, notebooks e periféricos.

# ☕ Java MySQL sistema OS

<img width=100% src="https://github.com/Lucasbarbosa332/Sistema-os/blob/main/Sistema%20OS/infox-master/assets/sistemaOS.png?raw=true"></img>

## Instruções para instalação e uso do aplicativo
# Pré requisistos 

1. Ter o Java versão 8 instalado (só funciona corretamente nesta versão do Java).

         https://www.java.com/pt-BR/

2. Ter um banco de dados local baseado no MySQL 8 ou MariaDB compatível, no exemplo usei o XAMPP que pode ser obtido no link indicado
        
        https://www.apachefriends.org/

# Instalação do banco

1. Iniciar os serviços Apache e MySQL no XAMPP, conforme indicado na imagem.

<img width=100% src="https://github.com/Lucasbarbosa332/Sistema-os/blob/main/xampp1.png"></img>

2.No navegador de internet digite: localhost/dashboard e selecione no menu: phpMyAdmin conforme indicado na imagem.

<img width=100% src="https://github.com/Lucasbarbosa332/Sistema-os/blob/main/xampp2.png"></img>


3. Crie um novo banco de dados de nome dbinfox conforme indicado na imagem.

<img width=100% src="https://github.com/Lucasbarbosa332/Sistema-os/blob/main/Sistema%20OS/infox-master/assets/infoxtela1.png?raw=true"></img>

4. Na aba SQL, copie e cole o código abaixo e execute. (Passos 1,2 e 3 indicados na imagem)


    # Exemplo de Banco de Dados SQL

Este repositório contém um exemplo de criação de tabelas para um sistema de ordens de serviço com usuários, clientes e ordens de serviço (OS).

## Estrutura do Banco de Dados copie todo codigo abaixo 

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

create table tbusuarios(iduser int primary key,usuario varchar(15) not null,fone varchar(15),login varchar(15) not null unique,senha varchar(250) not null,perfil varchar(20) not null);
insert into tbusuarios(iduser,usuario,login,senha,perfil) values(1,'Administrador','admin',md5('admin'),'admin');
create table tbclientes(idcli int primary key auto_increment,nomecli varchar(50) not null,endcli varchar(100),fonecli varchar(15) not null,emailcli varchar(50) unique);
create table tbos(os int primary key auto_increment,data_os timestamp default current_timestamp,tipo varchar(15) not null,situacao varchar(20) not null,equipamento varchar(150) not null,defeito varchar(150),servico varchar(150),tecnico varchar(30),valor decimal(10,2),idcli int not null,foreign key(idcli) references tbclientes(idcli));
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


<img width=100% src="https://github.com/Lucasbarbosa332/Sistema-os/blob/main/Sistema%20OS/infox-master/assets/infoxtela2.png?raw=true"></img>

# Instalação do aplicativo
1. Em Releases faça o download do arquivo dist.zip

2. Descompactar e executar o arquivo prjinfoX.jar Verifique na tela de login o ícone que representa o banco de dados conectado. Se estiver com erro (conforme indicado na figura) verifique o XAMPP e revise novamente os passos 1 a 4 da instalação do banco.
