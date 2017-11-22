create database dados_multimidia;

use dados_multimidia;

create table dados_multimidia (
Codigo int auto_increment not null,
Nome varchar(20),
Tipo varchar(20),
Dados longblob,
primary key (codigo) ) ;

SELECT @@GLOBAL.secure_file_priv;

insert into dados_multimidia (Codigo,Nome,Tipo,Dados) values ('1','Imagem','Teste', load_file("C:/wamp64/tmp/images.jpg"));
insert into dados_multimidia (Codigo,Nome,Tipo,Dados) values ('2','Imagem','Teste1', load_file("C:/wamp64/tmp/teste1.jpg"));
insert into dados_multimidia (Codigo,Nome,Tipo,Dados) values ('3','Imagem','Teste2', load_file("C:/wamp64/tmp/teste2.jpg"));
insert into dados_multimidia (Codigo,Nome,Tipo,Dados) values ('4','Imagem','Teste3', load_file("C:/wamp64/tmp/teste3.jpg"));

select * from dados_multimidia;

select Dados into dumpfile "C:/wamp64/tmp/images.jpg" from dados_multimidia where  Codigo= 1 ;
select Dados into dumpfile "C:/wamp64/tmp/teste1.jpg" from dados_multimidia where  Codigo= 2 ;
select Dados into dumpfile "C:/wamp64/tmp/teste2.jpg" from dados_multimidia where  Codigo= 3 ;
select Dados into dumpfile "C:/wamp64/tmp/teste3.jpg" from dados_multimidia where  Codigo= 4 ;





