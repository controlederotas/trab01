# TRABALHO 01:  Título do Trabalho
Trabalho desenvolvido durante a disciplina de BD1

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Italo Vaz Aurelio:vazitaloaurelio@gmail.com<br>
Luma Gonçalves:goncalves.luma010@gmail.com<br>
Ana Paula Martins:anapdiasguimaraes@gmail.com<br>
Rafael W. Sampogna:sampogna.rafael@gmail.com<br>

### 2.INTRODUÇÃO E MOTIVAÇAO<br>

A empresa Controle de Rotas tem como foco principal encontrar e apontar locais com maiores índices de criminalidade levando em conta os pontos de saída e chegada de caminhões transportadores de carga, afim de que a chegada ocorra de forma mais segura. Hoje, o Brasil ocupa a sexta posição na lista de países com maior índice de roubo de cargas e, sabendo deste dado, buscamos reunir informações sobre segurança de determinados locais e compará-los no nosso sistema, garantindo maior possibilidade de entrega correta de cargas bem como a segurança dos motoristas. Para isto, o sistema de controle de rotas proposto contará com um banco de dados que receberá informações de diversas fontes. Entre elas, relatórios de controle de criminalidade de cargas que podem ser encontrados na internet como principal fonte de alimentação e o próprio relato de usuários que tiveram experiências de furto ou algum outro tipo de crime. O sistema apontará áreas com maior incidência criminosa para que o motorista possa traçar uma melhor rota para a entrega.
 

### 3.MINI-MUNDO Novo<br>

O sistema proposto para a Controle de Rotas conterá as seguintes informações. Primeiramente o sistema precisa receber o local de origem e destino da entrega da mercadoria. Os dados armazenados referentes à essa etapa serão hora de saída do local de entrega, cep, rua, número, bairro e estado de cada uma das localidades. A proposta do sistema é conseguir mostrar os pontos mais violentos de determinada área. Essa área nada mais é que a região pertencente à origem e ao destino. Para exibir esses pontos, o sistema precisa ter acesso ao mapa da região e também ao índice de assaltos recorrentes correspondente àquela área. O mapa da região é composto por ruas. Os índices de assaltos são representados pela quantidade de registros de boletins de ocorrência para àquela localidade, juntamente com a data e hora de cada ocorrência. É possível também o usuário contribuir com o sistema informando no site da empresa as ocorrências de roubo/furto. Para registrar a ocorrência o usuário precisa fazer um login com e-mail e senha. Depois é preciso informar a cidade que aconteceu a ocorrência, o tipo de roubo, o tipo de item furtado, o sexo e a data e hora. Por meio de toda essa avaliação o sistema consegue mostrar ao usuário os pontos mais violentos desse percurso para que assim ele possa evitá-los.

### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>
Este é um prototipo das telas to sistema, um rascunho apenas, o mesmo pode sofrer alterações no decorrer do trabalho, todos os arquivos foram feitos com a ferramenta balsamic.


LINK DO PROTOTIPO ![clique aqui](https://github.com/controlederotas/trab01/blob/master/arquivos/controle%20de%20rotas.pdf?raw=true "PROTOTIPO ")
    


#### 4.1 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
    
A Controle de Rotas precisa inicialmente dos seguintes relatórios:
* Relatório informando dados do usuário.
* Relatório com registros dos pontos onde os usuários foram assaltados.
* Relatório com bairros de alto nível de periculosidade e hora do dia com maior índice de roubo.
* Relatório contendo origem e destino da mercadoria.
* Relatório contendo tipo deroubo e itens furtados dos usuários.
 
 
#### 4.2 TABELA DE DADOS DO SISTEMA:
A tabela macro contem algum dos itens que identificamos até agora, como é uma tabela inicial pode ser que tenha falta de muitos campos e afins, mas para efeito de comparação essa é a tabela incial e o que entendemos dela.
    
![Tabela de dados controle de rotas](https://github.com/controlederotas/trab01/blob/master/arquivos/tabelaControleDeRotas.xlsx?raw=true "Tabela - Controle de rotas")
    
>## Marco de Entrega 01 em: (30/08/2018)<br>

### 5.MODELO CONCEITUAL<br>
        
![Alt text](https://raw.githubusercontent.com/controlederotas/trab01/master/images/modelo_conceitual.png)
        
    
#### 5.1 Validação do Modelo Conceitual
    carroBD: Harrison Sanches, Matheus COmério, Luciano Ananias, Joao Augusto
    qr-bus: Ewerson Vieira, Giuliano de Paulo, Lorran Gabriel, Marcos Antônio

#### 5.2 DECISÕES DE PROJETO

a) Traçar rotas : Inicialmente, nosso projeto visava traçar a melhor rota com base no índice de criminalidade do ponto de saída da mercadoria ao ponto de seu ponto de chegada com base no índice de criminalidade em certos pontos desta rota. Junto ao professor e, dada a dificuldade encontrada para implementar o sistema que calculasse a melhor rota, decidimos que o sistema passaria a indicar pontos de maior e menor risco para o condutor, retirando a funcionalidade de cálculo de rotas.

b) Incluir boletim de ocorrência : Consideramos que uma forma dinâmica de manter nosso banco sempre atualizado seria dar ao usuário a possibilidade de registrar assaltos sofridos.

c) Coleta de dados de tabelas já existentes : Julgamos importante a coleta de dados vindo de diversas fontes abertas e confiáveis. Estas fontes alimentarão nosso banco e servirão de base para nosso banco de dados. Utilizaremos ferramentas já conhecidas para extrair estes dados. 




>## Marco de Entrega 02 em: (13/09/2018)<br>
#### 5.3 DESCRIÇÃO DOS DADOS 

    •USUARIO: Tabela que armazena informações relativas ao usuário.
    
      -EMAIL: Campo que armazena o email referente ao usuário.
      -SEXO: Campo que armazena o genêro do usuário com 'M' ou 'F'.
      -COD_USUARIO: Campo que armazena o código único do usuário.
    
    •BOLETIM: Tabela que armazena informações sobre boletins de ocorrência registrados.
    
      -DATA_ROUBO: Indica a data do roubo registrado no boletim.
      -HORA_ROUBO: Indica a hora do roubo registrado no boletim.
      -ITENS_ROUBO: Indica os itens roubados.
      -TIPO_ROUBO: Indica o tipo de roubo.
      -COD_BOLETIM: Indica o código único do boletim.
      -FK_COD_USUARIO: Campo que faz referência ao código de usuário, relacionando o boletim com o usuário que o fez.
    
    •ENTREGA: Tabela que contém informações a respeito da entrega.
    
      -ORIGEM: Campo que indica a origem da mercadoria.
      -DESTINO: Campo que indica o destino final da mercadoria.
      -COD_ENTREGA: Campo que indica o código único referente à entrega.
      -FK_COD_ENDERECO_ORIGEM: Campo que referencia ao código de endereço da origem da entrega.
      -FK_COD_ENDERECO_DESTINO: Campo que referencia ao código de endereço do destino da entrega.
    
    •CLIENTE: Tabela que contém informações relacionadas ao cliente(Interessado no transporte da mercadoria).
    
      -NOME: Campo contendo o nome do cliente.
      -EMAIL: Campo contendo o email do cliente.
      -SENHA: Campo contendo a senha escolhida pelo cliente.
      -CPF: Campo contendo o CPF do cliente.
    
    •ENDERECO: Tabela que armazena endereços.
    
      -RUA: Campo que armazena rua.
      -MUNICIPIO: Campo que armazena o município.
      -BAIRRO: Campo que armazena o bairro.
      -FK_COD_MUNICIPIO: Campo que faz referência ao código de um município para compor o endereço.
      -FK_CO_BAIRRO: Campo que faz referência ao código de um bairro para compor o endereço.
    
    •MUNICIPIO: Tabela que armazena os municípios.
    
      -NOME_MUNICIPIO: Campo que armazena o nome do município.
      -COD_MUNICIPIO: Campo que contém o código único do município.
      
    •BAIRRO: Tabela que armazena os bairros.
    
      -NOME_BAIRRO: Campo que armazena o nome dos bairros.
      -COD_BAIRRO: Campo que contém o código único do bairro.<br>
    


### 6	MODELO LÓGICO<br>

![Alt text](https://raw.githubusercontent.com/controlederotas/trab01/master/images/Lógico_2.png)

### 7	MODELO FÍSICO<br>
	
	
	CREATE TABLE usuario(
		cod SERIAL PRIMARY KEY NOT NULL,  
		email VARCHAR(60),
		sexo CHAR(1) 
	);

	CREATE TABLE cliente(
		cpf VARCHAR(14) PRIMARY KEY NOT NULL,
		nome VARCHAR(100),
		email VARCHAR(150),
		senha VARCHAR(30)
	);

	CREATE TABLE municipio(
	  	cod_municipio SERIAL PRIMARY KEY NOT NULL,
	  	nome_municipio VARCHAR(60)     
	);

	CREATE TABLE bairro(
		cod_bairro INTEGER PRIMARY KEY NOT NULL,
	  	nome_bairro VARCHAR(40),
	  	cod_municipio INTEGER,
	  	FOREIGN KEY (cod_municipio) REFERENCES municipio (cod_municipio)
	);

	CREATE TABLE endereco(
		cod_end INTEGER PRIMARY KEY,
	  	rua VARCHAR(60),
	  	cod_bairro INTEGER,
	  	cod_municipio INTEGER,
	  	FOREIGN KEY (cod_bairro) REFERENCES bairro(cod_bairro),
	  	FOREIGN KEY (cod_municipio) REFERENCES municipio(cod_municipio)
	);

	CREATE TABLE boletim(
		cod_boletim INTEGER PRIMARY KEY NOT NULL,
	  	data_roubo DATE,
	  	hora_roubo TIME,
	  	item_roubo VARCHAR(60),
	  	tipo_roubo VARCHAR(50),
	  	cod_endereco INTEGER,
	  	FOREIGN KEY(cod_endereco) REFERENCES endereco(cod_end)  
	);

	CREATE TABLE entrega(
	  	cod_entrega SERIAL PRIMARY KEY NOT NULL,
	  	cod_cliente VARCHAR(14),
	  	origem INTEGER,
	  	destino INTEGER,

	  	FOREIGN KEY(cod_cliente) REFERENCES cliente(cpf),
	  	FOREIGN KEY(origem) REFERENCES endereco(cod_end),
	  	FOREIGN KEY(destino) REFERENCES endereco(cod_end)
	);


### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
	INSERT INTO usuario 
	VALUES (194538, 'patricia.lima@hotmail.com', 'F'),
	(785632, 'luciana_almeida@hotmail.com', 'F'),
	(198500, 'pablorodrigues@gmail.com', 'M'),
	(987438, 'rodrigoxavier12@bol.com', 'M'),
	(693238, 'jose_almeida@hotmail.com', 'M'),
	(794133, 'guilherme.souza@gmail.com', 'M'),
	(824530, 'analopez@hotmail.com', 'F'),
	(634538, 'ada.lima@gmail.com', 'F'),
	(621548, 'filipebarcelos@hotmail.com', 'M'),
	(845538, 'luana_aragao@gmail.com', 'F');

	INSERT INTO municipio 
	VALUES (532066, 'Cariacica'),
	(530066, 'Viana'),
	(532666, 'Vila Velha'),
	(532000, 'Santa Tereza'),
	(100066, 'Vitória'),
	(538886, 'Marechal Floriano'),
	(123466, 'Domingos Martins'),
	(532088, 'Serra'),
	(112776, 'Aracruz'),
	(532444, 'Fundão');

	INSERT INTO bairro
	VALUES (000123, 'Coqueiral', 532666),
	(698623, 'Manguinhos', 532444),
	(000666, 'Campo Grande', 532066),
	(603203, 'Jardim América', 532066),
	(055423, 'Jacaraipe', 532088),
	(003130, 'Lanranjeiras', 532088),
	(204403, 'Morada', 112776),
	(002423, 'Mata da Praia', 100066),
	(003323, 'Manguinhos', 538886),
	(130123, 'Carapina', 532088);

	INSERT INTO endereco
	VALUES (1235963, 'Linhares', 000123, 532088),
	(6325963, 'Amélia Silva', 000666, 123466),
	(1265263, 'Cristovao Colombo', 000123, 532088),
	(9300163, 'Aleixo Neto', 002423, 100066),
	(1222003, 'Barreto Silva', 055423, 112776),
	(6238423, 'Luiz Lima', 000666, 123466),
	(1235300, 'Cerqueira Lima', 603203, 123466),
	(4288963, 'Assis Lopes', 055423, 532088),
	(1266963, 'Reta da Penha', 002423, 100066),
	(5235113, 'Fernando Ferrari', 130123, 100066);

	INSERT INTO boletim
	VALUES (9875632, '2018/06/30', '15:43:43', 'celular', 'roubo', 6325963),
	(2987632, '2018/06/28', '15:50:00', 'carteira', 'roubo', 1235963),
	(6375212, '2016/08/02', '17:21:12', 'mochila', 'roubo', 6325963),
	(2375032, '2018/06/30', '13:43:32', 'carro', 'roubo', 6325963),
	(6300632, '2018/07/26', '09:52:00', 'celular', 'roubo', 9300163),
	(1000332, '2017/03/13', '08:00:09', 'celular', 'roubo', 1222003),
	(8635632, '2018/01/25', '10:00:52', 'carteira', 'roubo', 1222003),
	(9870232, '2017/06/30', '19:10:47', 'celular', 'roubo', 4288963),
	(9878432, '2018/09/17', '18:30:20', 'mochila', 'roubo', 5235113),
	(6307896, '2018/09/27', '14:00:00', 'celular', 'roubo', 4288963);

	INSERT INTO cliente
	VALUES (12381736742, 'Luiz Gomes', 'luiz.barros@gmail.com', '123abc'),
	(12871736014, 'Amanda Santos', 'amanda@gmail.com', '1aba78'),
	(63384236702, 'Ana Maria Lopes', 'anam_lopes@hotmail.com', '36fa**'),
	(86210036742, 'Betina Santos', 'betina@gmail.com', '12*22c'),
	(18981734742, 'Luiz Gomes', 'luiz_gomess@gmail.com', '140*bdc'),
	(2438177430, 'Bruna Muniz', 'souzamuniz@hotmail.com', '163*50c'),
	(98765736742, 'Maria Antonieta', 'mari.ant@hotmail.com', 'bmlabc'),
	(86337936742, 'Luiz Miguel', 'luiz.miguel@gmail.com', '196+00'),
	(74382036742, 'Carla Silva Pereira', 'carlasilva@hotmail.com', 'bmd*0bc'),
	(62681936642, 'Isabela Guimarães', 'Isabela@gmail.com', '123510');

	INSERT INTO entrega
	VALUES (148869, 12381736742, 1235963, 1266963),
	(328746, 2438177430, 6325963, 5235113),
	(058832, 12871736014, 1265263, 1266963),
	(177779, 63384236702, 1235963, 4288963),
	(149969, 86210036742, 1235300, 1235300),
	(148810, 2438177430, 1222003, 6238423),
	(448209, 62681936642, 4288963, 1222003),
	(118817, 86210036742, 4288963, 9300163),
	(141969, 86210036742, 4288963, 1265263),
	(298828, 74382036742, 1266963, 6325963);

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELAS E INSERÇÃO DOS DADOS
	CREATE TABLE usuario (
		cod SERIAL PRIMARY KEY NOT NULL,  
		email VARCHAR(60),
		sexo CHAR(1) 
	);

	CREATE TABLE cliente(
		cpf VARCHAR(14) PRIMARY KEY NOT NULL,
		nome VARCHAR(100),
		email VARCHAR(150),
		senha VARCHAR(30)
	);

	CREATE TABLE municipio(
  		cod_municipio SERIAL PRIMARY KEY NOT NULL,
  		nome_municipio VARCHAR(60)     
	);

	CREATE TABLE bairro(
		cod_bairro INTEGER PRIMARY KEY NOT NULL,
  		nome_bairro VARCHAR(40),
  		cod_municipio INTEGER,
  		FOREIGN KEY (cod_municipio) REFERENCES municipio (cod_municipio)
	);

	CREATE TABLE endereco(
		cod_end INTEGER PRIMARY KEY,
  		rua VARCHAR(60),
  		cod_bairro INTEGER,
  		cod_municipio INTEGER,
  		FOREIGN KEY (cod_bairro) REFERENCES bairro(cod_bairro),
  		FOREIGN KEY (cod_municipio) REFERENCES municipio(cod_municipio)
	);

	CREATE TABLE boletim(
		cod_boletim INTEGER PRIMARY KEY NOT NULL,
  		data_roubo DATE,
  		hora_roubo TIME,
  		item_roubo VARCHAR(60),
  		tipo_roubo VARCHAR(50),
  		cod_endereco INTEGER,
  		FOREIGN KEY(cod_endereco) REFERENCES endereco(cod_end)  
	);

	CREATE TABLE entrega(
  		cod_entrega SERIAL PRIMARY KEY NOT NULL,
  		cod_cliente VARCHAR(14),
  		origem INTEGER,
  		destino INTEGER,

  		FOREIGN KEY(cod_cliente) REFERENCES cliente(cpf),
  		FOREIGN KEY(origem) REFERENCES endereco(cod_end),
  		FOREIGN KEY(destino) REFERENCES endereco(cod_end)
	);

	INSERT INTO usuario 
		VALUES (194538, 'patricia.lima@hotmail.com', 'F'),
		(785632, 'luciana_almeida@hotmail.com', 'F'),
		(198500, 'pablorodrigues@gmail.com', 'M'),
		(987438, 'rodrigoxavier12@bol.com', 'M'),
		(693238, 'jose_almeida@hotmail.com', 'M'),
		(794133, 'guilherme.souza@gmail.com', 'M'),
		(824530, 'analopez@hotmail.com', 'F'),
		(634538, 'ada.lima@gmail.com', 'F'),
		(621548, 'filipebarcelos@hotmail.com', 'M'),
		(845538, 'luana_aragao@gmail.com', 'F');

	INSERT INTO municipio 
		VALUES (532066, 'Cariacica'),
		(530066, 'Viana'),
		(532666, 'Vila Velha'),
		(532000, 'Santa Tereza'),
		(100066, 'Vitória'),
		(538886, 'Marechal Floriano'),
		(123466, 'Domingos Martins'),
		(532088, 'Serra'),
		(112776, 'Aracruz'),
		(532444, 'Fundão');

	INSERT INTO bairro
		VALUES (000123, 'Coqueiral', 532666),
		(698623, 'Manguinhos', 532444),
		(000666, 'Campo Grande', 532066),
		(603203, 'Jardim América', 532066),
		(055423, 'Jacaraipe', 532088),
		(003130, 'Laranjeiras', 532088),
		(204403, 'Morada', 112776),
		(002423, 'Mata da Praia', 100066),
		(003323, 'Manguinhos', 538886),
		(130123, 'Carapina', 532088);

	INSERT INTO endereco
		VALUES (1235963, 'Linhares', 000123, 532088),
		(6325963, 'Amélia Silva', 000666, 123466),
		(1265263, 'Cristovao Colombo', 000123, 532088),
		(9300163, 'Aleixo Neto', 002423, 100066),
		(1222003, 'Barreto Silva', 055423, 112776),
		(6238423, 'Luiz Lima', 000666, 123466),
		(1235300, 'Cerqueira Lima', 603203, 123466),
		(4288963, 'Assis Lopes', 055423, 532088),
		(1266963, 'Reta da Penha', 002423, 100066),
		(5235113, 'Fernando Ferrari', 130123, 100066);

	INSERT INTO boletim
		VALUES (9875632, '2018/06/30', '15:43:43', 'celular', 'roubo', 6325963),
		(2987632, '2018/06/28', '15:50:00', 'carteira', 'roubo', 1235963),
		(6375212, '2016/08/02', '17:21:12', 'mochila', 'roubo', 6325963),
		(2375032, '2018/06/30', '13:43:32', 'carro', 'roubo', 6325963),
		(6300632, '2018/07/26', '09:52:00', 'celular', 'roubo', 9300163),
		(1000332, '2017/03/13', '08:00:09', 'celular', 'roubo', 1222003),
		(8635632, '2018/01/25', '10:00:52', 'carteira', 'roubo', 1222003),
		(9870232, '2017/06/30', '19:10:47', 'celular', 'roubo', 4288963),
		(9878432, '2018/09/17', '18:30:20', 'mochila', 'roubo', 5235113),
		(6307896, '2018/09/27', '14:00:00', 'celular', 'roubo', 4288963);

	INSERT INTO cliente
		VALUES (12381736742, 'Luiz Gomes', 'luiz.barros@gmail.com', '123abc'),
		(12871736014, 'Amanda Santos', 'amanda@gmail.com', '1aba78'),
		(63384236702, 'Ana Maria Lopes', 'anam_lopes@hotmail.com', '36fa**'),
		(86210036742, 'Betina Santos', 'betina@gmail.com', '12*22c'),
		(18981734742, 'Luiz Gomes', 'luiz_gomess@gmail.com', '140*bdc'),
		(2438177430, 'Bruna Muniz', 'souzamuniz@hotmail.com', '163*50c'),
		(98765736742, 'Maria Antonieta', 'mari.ant@hotmail.com', 'bmlabc'),
		(86337936742, 'Luiz Miguel', 'luiz.miguel@gmail.com', '196+00'),
		(74382036742, 'Carla Silva Pereira', 'carlasilva@hotmail.com', 'bmd*0bc'),
		(62681936642, 'Isabela Guimarães', 'Isabela@gmail.com', '123510');

	INSERT INTO entrega
		VALUES (148869, 12381736742, 1235963, 1266963),
		(328746, 2438177430, 6325963, 5235113),
		(058832, 12871736014, 1265263, 1266963),
		(177779, 63384236702, 1235963, 4288963),
		(149969, 86210036742, 1235300, 1235300),
		(148810, 2438177430, 1222003, 6238423),
		(448209, 62681936642, 4288963, 1222003),
		(118817, 86210036742, 4288963, 9300163),
		(141969, 86210036742, 4288963, 1265263),
		(298828, 74382036742, 1266963, 6325963);

#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script
        (Drop para exclusão de tabelas + create para tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL
>## Marco de Entrega 03 em: (27/09/18) <br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>

>## Marco de Entrega 04 em: (18/10/2017)<br>

#### 9.6	CONSULTAS COM JUNÇÃO E ORDENAÇÃO (Mínimo 6)<br>
        a) Uma junção que envolva todas as tabelas possuindo no mínimo 3 registros no resultado
        b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho
#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho
#### 9.10	SUBCONSULTAS (Mínimo 3)<br>
### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO FINAL (Mínimo 6 e Máximo 10)<br>

### 11 Backup completo do banco de dados postgres 
    a) deve ser realizado no formato "backup" 
        (Em Dump Options #1 Habilitar opções Don't Save Owner e Privilege)
    b) antes de postar o arquivo no git o mesmo deve ser testado/restaurado por outro grupo de alunos/dupla
    c) informar aqui o grupo de alunos/dupla que realizou o teste.

### 12	TUTORIAL COMPLETO DE PASSOS PARA RESTAURACAO DO BANCO E EXECUCAO DE PROCEDIMENTOS ENVOLVIDOS NO TRABALHO PARA OBTENÇÃO DOS RESULTADOS<br>
        a) Outros grupos deverão ser capazes de restaurar o banco 
        b) executar todas as consultas presentes no trabalho
        c) executar códigos que tenham sido construídos para o trabalho 
        d) realizar qualquer procedimento executado pelo grupo que desenvolveu o trabalho
        
### 13   DIFICULDADES ENCONTRADAS PELO GRUPO<br>
>## Marco de Entrega Final em: (08/11/2018)<br>
        
### 14  FORMATACAO NO GIT: https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/



    

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. Caso existam arquivos com conteúdos sigilosos, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://sis4.com/brModelo/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


