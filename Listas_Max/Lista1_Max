create database BANCO;

create table banco (
codigo int not null,
nome varchar(100) not null,
primary key (codigo)
);


create table agencia (
cod_banco int(10) ,
numero_ag varchar(25) not null,
endereco varchar(100) not null,
primary key (cod_banco),
foreign key	(cod_banco) references banco(codigo)
);

create table cliente (
cpf varchar (15) ,
nome varchar(100) not null,
sexo varchar(45) not null,
endereco varchar(100) not null,
primary key (cpf)
);

create table conta (
numero_conta varchar(25) ,
saldo double not null,
tipo_conta varchar(45) not null,
num_agencia int not null,
primary key (numero_conta),
foreign key	(num_agencia) references agencia(numero_ag)
);

create table historico (
cpf_cliente varchar (15) not null,
num_conta	varchar(25)	not	null,
data_inicio date not null,
primary key	(cpf_cliente),
foreign key	(cpf_cliente) references cliente(cpf),
foreign key	(num_conta) references	conta(numero_conta)
);

create table telefone_cliente (
cpf_cli varchar (15) not null,
telefone varchar(40),
primary key (cpf_cli),
foreign key	(cpf_cli) references	cliente(cpf)
);

insert	into banco (codigo,nome) values('1','Banco do Brasil');
insert	into banco (codigo,nome) values('4','CEF');

insert	into agencia (numero_ag,endereco,cod_banco) values ('0562','Rua Joaquim Teixeira Alves, 1555','4');
insert	into agencia (numero_ag,endereco,cod_banco) values ('3153','Av. Marcelino Pires, 1960','1');

insert 	into cliente (cpf, nome,sexo,endereco) values ('111.222.333-44','Jennifer','F','Rua Cuiabá, 1050');
insert 	into cliente (cpf, nome,sexo,endereco) values ('666.777.888-99','Caetano K Lima','M','Rua Ivinhema, 879');
insert 	into cliente (cpf, nome,sexo,endereco) values ('555.444.777-33','Silvia Macedo','F','Rua Estados Unidos, 735');

insert 	into conta (numero_conta,saldo,tipo_conta,num_agencia) values ('86340-2','763.05','2','3153');
insert 	into conta (numero_conta,saldo,tipo_conta,num_agencia) values ('2358-7','3879.12','1','0562');

insert	into historico (cpf_cliente,num_conta,data_inicio) values ('111.222.333-44','23584-7','1997-12-17');
insert	into historico (cpf_cliente,num_conta,data_inicio) values ('666.777.888-99','23584-7','1997-12-17');
insert	into historico (cpf_cliente,num_conta,data_inicio) values ('555.444.777-33','86340-2','2010-11-29');

insert 	into telefone_cliente (cpf_cli,telefone) values ('111.222.333-44','(67)3422-7788');
insert 	into telefone_cliente (cpf_cli,telefone) values ('666.777.888-99','(67)3423-9900,(67)8121-8833');

alter table cliente add email varchar(25);

select cpf, endereco from cliente where nome = 'Paulo A Lima';

select a.numero_ag, a.endereco from agencia as a join banco as b on b.codigo = a.cod_banco where codigo = 'Banco_do Brasil';

select c.numero_conta, c.num_agencia , cl.nome from conta as c join historico as h on c.numero_conta = h.num_conta join cliente as cl on cl.cpf = h.cpf_cliente;

select c.saldo from conta as c join historico as h on c.numero_conta = h.num_conta join cliente as cl on cl.cpf = h.cpf_cliente where cl.sexo = 'M';

select * from conta as c  inner join agencia as a  on c.num_agencia = a.numero_ag  where num_agencia = '0562';

delete from conta where numero_conta = '86340-2';

SET SQL_SAFE_UPDATES = 0;

update agencia as a set  a.numero_ag = '6342' where a.numero_ag = '0562';

update cliente as c set c.email =  'caetanolima@gmail.com' where c.nome = 'Caetano K';

update conta set saldo = saldo + 10 where numero_conta = '23584-7'; 