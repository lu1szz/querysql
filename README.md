https://compilebytes.com/share/myCUlyYSzqhttps://compilebytes.com/share/myCUlyYSzq

show databases;

show tables;

CREATE TABLE usuario (
  id_usuario INT AUTO_INCREMENT PRIMARY KEY,
  nome varchar (255) NOT NULL,
  email varchar (255) NOT NULL UNIQUE,
  senha varchar (255) NOT NULL,
  data_nascimento DATE NULL
);

CREATE TABLE perfil (
  id_perfil INT AUTO_INCREMENT PRIMARY KEY,
  data_criacao TIMESTAMP NOT NULL, 
  nome_usuario varchar(255) NULL,
  biografia varchar(255) NULL,
  pronome varchar (255) NULL
);

CREATE TABLE pesquisa(
  id_pesquisa INT AUTO_INCREMENT PRIMARY KEY,
  conteudo varchar(255) NULL,
  data_pesquisa TIMESTAMP NOT NULL
);

CREATE TABLE publicacao(
  id_publicacao INT AUTO_INCREMENT PRIMARY KEY,
  data_postagem TIMESTAMP NOT NULL,
  descricao varchar (255) NULL,
  conteudo varchar (255) NULL
);

CREATE TABLE compartilhamento (
  id_compartilhamento INT AUTO_INCREMENT PRIMARY KEY,
  id_publicacao INT NOT NULL,
  id_usuario INT NOT NULL,
  data_compartilhamento TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
  local_compartilhamento VARCHAR(255) NOT NULL,
  FOREIGN KEY (id_publicacao) REFERENCES publicacao(id_publicacao),
  FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario)
);


desc usuario;

show create table usuario;

/*usuario*/
insert into usuario(nome, email, senha, data_nascimento)
values ('Luis Oliveira','example@gmail.com','12345','2002-10-20');

/*perfil*/
insert into perfil (id_perfil, data_criacao, nome_usuario, biografia, pronome)
values ('1', '2002-10-20', 'Luis', 'Me chamo fulano', 'ele/dele');

/*pesquisa*/
insert into pesquisa(id_pesquisa, conteudo, data_pesquisa)
values ('1','conteudo da pesquisa','2019-10-12');

/* publicacao*/
insert into publicacao(id_publicacao, data_postagem, descricao, conteudo)
values ('1','2026-10-27','fruta','alimento');

/* compartilhamento*/
insert into compartilhamento(id_publicacao, id_usuario, data_compartilhamento, local_compartilhamento)
values ('1','1','2026-10-27','Brasil');

select * from compartilhamento;

