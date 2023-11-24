# BD-NORMALIZÇÃO


## Etapa 1: Criação de Tabelas e Inserção de Dados

```
create table veiculos(
	cod_Locacao int primary key auto_increment not null,
	veiculo	varchar (80) not null,
	cor varchar(80) not null,
	placa varchar (50) not null,
	diaria decimal(9,2) not null,	
	cliente varchar(80) not null,
	cpf varchar(80) not null,
	nascimento date not null,
	dia int not null,
	total decimal(9,2) not null
);
create table cliente(
	cpf varchar(80) primary key not null,
	nome varchar(80) not null,
	nascimento date 
);
    
create table veiculo(
	cod_locacao int primary key auto_increment not null,
	veiculo varchar(80) not null,
	cor varchar(80) not null,
	placa varchar(80) not null,
	diaria decimal(9,2) not null,
	cpf_cli varchar(80) not null,
	dia int not null,
	total decimal(9,2) not null,
	foreign key (cpf_cli) references cliente(cpf)
);
```
## Etapa 1-2: Inserção de Dados
```
insert into cliente (cpf, nome, nascimento) values ('123.456.789-01','Ariano Sussuna','2022-05-21'),
insert into cliente (cpf, nome, nascimento) values ('543.765.987-23','Grace Hopper','2002-04-29'),
insert into cliente (cpf, nome, nascimento) values ('987.654.321-90','Richard Feynman','2001-10-12'),
insert into cliente (cpf, nome, nascimento) values ('432.765.678-67','Edgar Poe','1998-12-14'),
insert into cliente (cpf, nome, nascimento) values ('927.384.284-44','Gordon Freeman','1984-11-26'),
    
select* from cliente;
    
insert into veiculo (veiculo, cor , placa , diaria, cpf_cliente,dia, total) values ('Fusca','Preto', 'WER-3456',30.00, '123.456.789-01',3, 90.00),
insert into veiculo (veiculo, cor , placa , diaria, cpf_cliente,dia, total) values ('Variante','Rosa', 'FDS-8384',60.00, '543.765.987-23',7, 420.00),
insert into veiculo (veiculo, cor , placa , diaria, cpf_cliente,dia, total) values ('Comodoro','Preto', 'CVB-9933',20.00, '987.654.321-90',1, 20.00),
insert into veiculo (veiculo, cor , placa , diaria, cpf_cliente,dia, total) values ('Deloriam','Azul', 'FGH-2256',30.00, '123.456.789-01',3, 90.00),
insert into veiculo (veiculo, cor , placa , diaria, cpf_cliente,dia, total) values ('Brasilia','amarela', 'DDI-3948',45.00, '927.384.284-44',7, 315.00),

select * from veiculo;
```

## Etapa 1-3:Criaçao das views
```
create view Todas_locacoes as
	select * from veiculo
	join cliente on cliente.cpf = veiculo.cpf_cliente;
    
    select * from Todas_locacoes;
```
## Etapa 1-4:Print View , Modelo Logico
![exer1-4-1]().
![exer1-4-2](https://github.com/Ig0rFA/BD-NORMALIZA-O/blob/main/PrintAutomoveis.png).


