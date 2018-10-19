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
        
![Alt text](https://raw.githubusercontent.com/controlederotas/trab01/master/images/modelo_conceitual_novo.png)
        
    
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
      	-TIPO_ROUBO: Indica o tipo de roubo.
      	-COD_BOLETIM: Indica o código único do boletim.
      	-ID: Chave primária que faz referência ao código de usuário, relacionando o boletim com o usuário que o fez.
    
    •ENTREGA: Tabela que contém informações a respeito da entrega.
    
    	-COD_ENTREGA: Campo que indica o código único referente à entrega.
      	-Destino_entrega: Campo que referencia ao código de endereço da origem da entrega. (Chave primária)
    
    •CLIENTE: Tabela que contém informações relacionadas ao cliente(Interessado no transporte da mercadoria).
    
      	-NOME: Campo contendo o nome do cliente.
      	-EMAIL: Campo contendo o email do cliente.
      	-SENHA: Campo contendo a senha escolhida pelo cliente.
      	-CPF: Campo contendo o CPF do cliente.
      
    •PESSOA: Tabela que guarda informações referentes à uma pessoa, cliente do sistema ou não.
    
    	- ID: Chave primária contendo um identificador da pessoa.
	- Nome: Campo que indica o nome da pessoa.
	- Email: Campo que indica o email referente à uma pessoa.
	
    •FÍSICA: Tabela que guarda informações do tipo pessoa física.
    	
	- CPF: Campo que guarda o CPF de uma pessoa física.
	- Sexo: Campo que indica o sexo de uma pessoa.

    •JURÍDICA: Tabela que guarda informações do tipo pessoa jurídica.
    
    	- CNPJ: Campo que guarda o CNPJ de uma pessoa jurídica.
	
    •CLIENTE: Tabela que guarda informações relevantes ao cliente.
    
    	- Senha: Campo que armazena a senha de um cliente.
	
    
    •ENDERECO: Tabela que armazena endereços.
    
      -Tipo_logradouro: Campo que armazena o tipo de logradouro referente a um endereço(Rua, avenida...).
      -Cod_end
    
    •MUNICIPIO: Tabela que armazena os municípios.
    
      -NOME_MUNICIPIO: Campo que armazena o nome do município.
      -COD_MUNICIPIO: Campo que contém o código único do município.
      
    •BAIRRO: Tabela que armazena os bairros.
    
      -NOME_BAIRRO: Campo que armazena o nome dos bairros.
      -COD_BAIRRO: Campo que contém o código único do bairro.
      
    •CONTATO: Tabela que armazena um contato de um usuário.
    
    	- Contato_cliente: Campo que armazena uma forma de contato ao cliente.
	- Cod_contato: Campo que armazena o código do tipo de contato relacionado ao inserido no campo "Contato_cliente".
	
    •TIPO_DE_CONTATO: Tabela que armazena os tipos de contato.
    
   	- Tipo_contato: Campo que armazena os tipos de contato possíveis. 
	- Cod_tipo_contato: Campo que armazena o código do tipo de contato do cliente.
	
	
    


### 6	MODELO LÓGICO<br>

![Alt text](https://raw.githubusercontent.com/controlederotas/trab01/master/images/logico_18_10.png)

### 7	MODELO FÍSICO<br>
	
	/* Lógico_novo: */

	CREATE TABLE PESSOA (
    	Email VARCHAR,
    	ID SERIAL PRIMARY KEY,
    	Nome VARCHAR
	);

	CREATE TABLE ENDERECO (
	    Tipo_logradouro VARCHAR,
	    Cod_end SERIAL PRIMARY KEY,
	    FK_MUNICIPIO_Cod_municipio INT,
	    FK_Logradouro_Cod_logradouro INT
	);

	CREATE TABLE MUNICIPIO (
	    Cod_municipio INT PRIMARY KEY,
	    Nome_municipio VARCHAR,
	    FK_BAIRRO_Cod_bairro INT
	);

	CREATE TABLE BOLETIM (
	    Data_roubo DATE,
	    Hora_roubo TIME,
	    ID SERIAL PRIMARY KEY,
	    Cod_tipo INT,
	    Cod_item INT,
	    FK_ENDERECO_Cod_end SERIAL,
	    FK_PESSOA_ID SERIAL
	);

	CREATE TABLE BAIRRO (
	    Cod_bairro INT PRIMARY KEY,
	    Nome_bairro VARCHAR
	);

	CREATE TABLE FISICA (
	    Sexo CHAR,
	    CPF VARCHAR,
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE JURIDICA (
	    CNPJ VARCHAR,
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE CLIENTE (
	    Senha VARCHAR,
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE TIPO_ROUBO (
	    Tipo VARCHAR,
	    Cod_tipo SERIAL PRIMARY KEY,
	    FK_BOLETIM_ID SERIAL
	);

	CREATE TABLE ITEM_ROUBO (
	    Item VARCHAR,
	    Cod_item SERIAL PRIMARY KEY,
	    FK_BOLETIM_ID SERIAL
	);

	CREATE TABLE Logradouro (
	    Cod_logradouro INT PRIMARY KEY,
	    Tipo_logradouro VARCHAR
	);

	CREATE TABLE CONTATO (
	    Contato_cliente VARCHAR,
	    FK_PESSOA_ID SERIAL,
	    FK_TIPO_DE_CONTATO_Cod_tipo_contato VARCHAR
	);

	CREATE TABLE TIPO_DE_CONTATO (
	    Cod_tipo_contato VARCHAR PRIMARY KEY,
	    Tipo_contato VARCHAR
	);

	CREATE TABLE ENTREGA (
	    FK_PESSOA_ID SERIAL,
	    FK_ENDERECO_Cod_end SERIAL,
	    Destino_entrega VARCHAR,
	    Cod_entrega SERIAL PRIMARY KEY
	);

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_2
	    FOREIGN KEY (FK_MUNICIPIO_Cod_municipio)
	    REFERENCES MUNICIPIO (Cod_municipio)
	    ON DELETE RESTRICT;

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_3
	    FOREIGN KEY (FK_Logradouro_Cod_logradouro)
	    REFERENCES Logradouro (Cod_logradouro)
	    ON DELETE RESTRICT;

	ALTER TABLE MUNICIPIO ADD CONSTRAINT FK_MUNICIPIO_2
	    FOREIGN KEY (FK_BAIRRO_Cod_bairro)
	    REFERENCES BAIRRO (Cod_bairro)
	    ON DELETE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_2
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE CASCADE;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_3
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT;

	ALTER TABLE FISICA ADD CONSTRAINT FK_FISICA_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE;

	ALTER TABLE JURIDICA ADD CONSTRAINT FK_JURIDICA_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE;

	ALTER TABLE CLIENTE ADD CONSTRAINT FK_CLIENTE_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE;

	ALTER TABLE TIPO_ROUBO ADD CONSTRAINT FK_TIPO_ROUBO_2
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE CASCADE;

	ALTER TABLE ITEM_ROUBO ADD CONSTRAINT FK_ITEM_ROUBO_2
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE CASCADE;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_2
	    FOREIGN KEY (FK_TIPO_DE_CONTATO_Cod_tipo_contato)
	    REFERENCES TIPO_DE_CONTATO (Cod_tipo_contato)
	    ON DELETE CASCADE;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_3
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE SET NULL;	


### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
	INSERT INTO PESSOA
	VALUES ('patricia.lima@hotmail.com', 194538, 'Patricia Lima'),
	('luciana_almeida@hotmail.com', 785632, 'Luciana Fernandes'),
	('pablorodrigues@gmail.com', 198500,  'Pablo Rodrigues'),
	('rodrigoxavier12@bol.com', 987438, 'Rodrigo Xavier'),
	('jose_almeida@hotmail.com', 693238,  'José Luiz'),
	('guilherme.souza@gmail.com', 794133, 'Guilhermede Souza'),
	('analopez@hotmail.com', 824530, 'Ana Luiza Lopes'),
	('ada.lima@gmail.com', 634538, 'Ada Lima'),
	('filipebarcelos@hotmail.com', 621548, 'Filipe Barcelos'),
	('luana_aragao@gmail.com', 845538, 'Luana Aragão'),
	('lali_magazine@lali.com', 435876, 'Lali Magazine'),
	('livraria@livraria.com.br', 678123, 'Livraria Livros'),
	('eletronicos@eletronicos.com', 234000, 'Eletrônica El'), 
	('comercial@comercial.com', 885876, 'Comercial Pereira'),
	('cosmeticosbia@cosmeticosbia.com.br', 228123, 'Bia Cosméticos'),
	('moveis@moveismol.com', 211000, 'Moveis MOl'),
	('Vinhosxc@hotmail.com', 400876, 'Vinhos XC'),
	('livrarialemos@gmail.com.br', 678003, 'Livraria Lemos'),
	('eletronicos123@eletronicos.com', 235500, 'Eletrônica 123'),
	('lojas@gmail.com', 499876, 'Loja da Maria');

	INSERT INTO BAIRRO
	VALUES (000123, 'Coqueiral'),
	(698623, 'Manguinhos'),
	(000666, 'Campo Grande'),
	(603203, 'Jardim América'),
	(055423, 'Jacaraipe'),
	(003130, 'Lanranjeiras'),
	(204403, 'Morada'),
	(002423, 'Mata da Praia'),
	(003323, 'Santa Cruz'),
	(130123, 'Centro'),
	(098765, 'Campinho');

	INSERT INTO MUNICIPIO
	VALUES (532066, 'Cariacica', 000666), 
	(830066, 'Viana', 204403),
	(532666, 'Vila Velha', 000123),
	(032000, 'Santa Tereza', 204403),
	(100066, 'Vitória', 002423),
	(738886, 'Marechal Floriano', 003323),
	(123466, 'Domingos Martins', 098765),
	(532088, 'Serra', 698623),
	(112776, 'Aracruz', 003323),
	(532444, 'Fundão', 130123);

	INSERT INTO LOGRADOURO
	VALUES (081, 'Rua'),
	(008, 'Avenida'),
	(090, 'Rodovia'),
	(001, 'Ponte'),
	(022, 'Beco'),
	(011, 'Ferrovia'),
	(485, 'Condominio'),
	(030, 'Escada'),
	(031, 'Estrada'),
	(036, 'Reta');

	INSERT INTO ENDERECO
	VALUES ('rua', 1234565, 532066, 081),                           
	('rua', 1131515, 830066, 081),
	('avenida', 0034565, 532666, 008),
	('rodovia', 1224565, 032000, 090),
	('escada', 1234465, 100066, 030),
	('estrada', 1234555, 123466, 031),
	('rua', 3235585, 532088, 081),
	('avenida', 7234765, 532666, 081),
	('rua', 0230565, 100066, 081),
	('rua', 1236566, 100066, 081);

	INSERT INTO BOLETIM
	VALUES ('2018/06/30', '15:43:43', 9875632, 1, 2, 1234565, 194538),
	('2018/06/28', '15:50:00', 2987632, 1, 1, 1131515, 785632),
	('2016/08/02', '17:21:12', 6375212, 2, 5, 1131515, 987438),
	('2018/06/30', '13:43:32', 2375032, 1, 8, 0034565, 198500),
	('2018/07/26', '09:52:00', 6300632, 2, 4, 3235585, 693238),
	('2017/03/13', '08:00:09', 1000332, 1, 4, 1234555, 794133),
	('2018/01/25', '10:00:52', 8635632, 1, 9, 1234465, 824530),
	('2017/06/30', '19:10:47', 9870232, 1, 7, 1236566, 824530),
	('2018/09/17', '18:30:20', 9878432, 2, 5, 7234765, 634538),
	('2018/09/27', '14:00:00', 6307896, 1, 6, 0230565, 621548);

	INSERT INTO FISICA
	VALUES('F', '12345678901', 194538),
	('F', '11315618911', 785632),
	('M', '22325628902', 198500),
	('F', '32343673901', 987438),
	('M', '72545978101', 693238),
	('M', '14345618901', 794133),
	('M', '92045618904', 824530),
	('F', '72385618901', 634538),
	('F', '12645078902', 845538);

	INSERT INTO JURIDICA
	VALUES ('67362129000110', 435876),
	('67262729000112', 678123),
	('47362129000113', 234000),
	('65362529000115', 885876),
	('77362169000160', 228123),
	('77372129000170', 211000),
	('97362129000199', 400876),
	('67369199000110', 678003),
	('87368129000118', 235500),
	('57365129000115', 499876);

	INSERT INTO CLIENTE
	VALUES ('abc123**', 435876),
	('cde123**', 678123),
	('22g-3', 234000),
	('fh(2)', 885876),
	('12_dGb', 211000),
	('568hh', 845538),
	('abc123&', 634538),
	('@gh*1', 794133),
	('123456', 693238),
	('gt5tu1', 194538);

	INSERT INTO TIPO_ROUBO
	VALUES ('Roubo', 1, 9875632),
	('Furto', 2, 6375212);

	INSERT INTO ITEM_ROUBO
	VALUES ('Mochila', 1, 2987632),
	('Celular', 2, 9875632),
	('Carro', 4, 6300632),
	('Bicicleta', 5, 6375212),
	('Carteira', 6, 6307896),
	('Joia', 7, 9870232),
	('Motocicleta', 8, 2375032),
	('Dinheiro', 9, 8635632);

	INSERT INTO TIPO_DE_CONTATO
	VALUES (22, 'Telefone pessoal'),
	(33, 'Celular pessoal'),
	(34, 'Celular comercial'),
	(45, 'Telefone comercial');

	INSERT INTO CONTATO
	VALUES (33312356, 785632, 22),
	(990867754, 198500, 33),
	(991234567, 987438, 33),
	(999234567, 794133, 33),
	(33215678, 824530, 22),
	(32098765, 634538, 22),
	(33781234, 621548, 45),
	(33320987, 499876, 45),
	(970987654, 235500, 34),
	(999768032, 885876, 34);

	INSERT INTO ENTREGA
	VALUES (785632, 1234565, 'Cariacica', 22567),
	(198500, 0034565, 'Vila Velha', 90567),
	(987438, 1234465, 'Vitória', 21260),
	(794133, 3235585, 'Serra', 33569),
	(634538, 1131515, 'Viana', 42761),
	(499876, 1234565, 'Cariacica', 42509),
	(235500, 0230565, 'Vitória', 02067),
	(885876, 3235585, 'Serra', 62567);

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELAS E INSERÇÃO DOS DADOS
	

	CREATE TABLE PESSOA (
	    Email VARCHAR,
	    ID SERIAL PRIMARY KEY,
	    Nome VARCHAR
	);

	CREATE TABLE ENDERECO (
	    Tipo_logradouro VARCHAR,
	    Cod_end SERIAL PRIMARY KEY,
	    FK_MUNICIPIO_Cod_municipio INT,
	    FK_Logradouro_Cod_logradouro INT
	);

	CREATE TABLE MUNICIPIO (
	    Cod_municipio INT PRIMARY KEY,
	    Nome_municipio VARCHAR,
	    FK_BAIRRO_Cod_bairro INT
	);

	CREATE TABLE BOLETIM (
	    Data_roubo DATE,
	    Hora_roubo TIME,
	    ID SERIAL PRIMARY KEY,
	    Cod_tipo INT,
	    Cod_item INT,
	    FK_ENDERECO_Cod_end SERIAL,
	    FK_PESSOA_ID SERIAL
	);

	CREATE TABLE BAIRRO (
	    Cod_bairro INT PRIMARY KEY,
	    Nome_bairro VARCHAR
	);

	CREATE TABLE FISICA (
	    Sexo CHAR,
	    CPF VARCHAR,
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE JURIDICA (
	    CNPJ VARCHAR,
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE CLIENTE (
	    Senha VARCHAR,
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE TIPO_ROUBO (
	    Tipo VARCHAR,
	    Cod_tipo SERIAL PRIMARY KEY,
	    FK_BOLETIM_ID SERIAL
	);

	CREATE TABLE ITEM_ROUBO (
	    Item VARCHAR,
	    Cod_item SERIAL PRIMARY KEY,
	    FK_BOLETIM_ID SERIAL
	);

	CREATE TABLE Logradouro (
	    Cod_logradouro INT PRIMARY KEY,
	    Tipo_logradouro VARCHAR
	);

	CREATE TABLE CONTATO (
	    Contato_cliente VARCHAR,
	    FK_PESSOA_ID SERIAL,
	    FK_TIPO_DE_CONTATO_Cod_tipo_contato VARCHAR
	);

	CREATE TABLE TIPO_DE_CONTATO (
	    Cod_tipo_contato VARCHAR PRIMARY KEY,
	    Tipo_contato VARCHAR
	);

	CREATE TABLE ENTREGA (
	    FK_PESSOA_ID SERIAL,
	    FK_ENDERECO_Cod_end SERIAL,
	    Destino_entrega VARCHAR,
	    Cod_entrega SERIAL PRIMARY KEY
	);

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_2
	    FOREIGN KEY (FK_MUNICIPIO_Cod_municipio)
	    REFERENCES MUNICIPIO (Cod_municipio)
	    ON DELETE RESTRICT;

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_3
	    FOREIGN KEY (FK_Logradouro_Cod_logradouro)
	    REFERENCES Logradouro (Cod_logradouro)
	    ON DELETE RESTRICT;

	ALTER TABLE MUNICIPIO ADD CONSTRAINT FK_MUNICIPIO_2
	    FOREIGN KEY (FK_BAIRRO_Cod_bairro)
	    REFERENCES BAIRRO (Cod_bairro)
	    ON DELETE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_2
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE CASCADE;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_3
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT;

	ALTER TABLE FISICA ADD CONSTRAINT FK_FISICA_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE;

	ALTER TABLE JURIDICA ADD CONSTRAINT FK_JURIDICA_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE;

	ALTER TABLE CLIENTE ADD CONSTRAINT FK_CLIENTE_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE;

	ALTER TABLE TIPO_ROUBO ADD CONSTRAINT FK_TIPO_ROUBO_2
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE CASCADE;

	ALTER TABLE ITEM_ROUBO ADD CONSTRAINT FK_ITEM_ROUBO_2
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE CASCADE;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_2
	    FOREIGN KEY (FK_TIPO_DE_CONTATO_Cod_tipo_contato)
	    REFERENCES TIPO_DE_CONTATO (Cod_tipo_contato)
	    ON DELETE CASCADE;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_2
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_3
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE SET NULL;
	
	
	
	INSERT INTO PESSOA
	VALUES ('patricia.lima@hotmail.com', 194538, 'Patricia Lima'),
	('luciana_almeida@hotmail.com', 785632, 'Luciana Fernandes'),
	('pablorodrigues@gmail.com', 198500,  'Pablo Rodrigues'),
	('rodrigoxavier12@bol.com', 987438, 'Rodrigo Xavier'),
	('jose_almeida@hotmail.com', 693238,  'José Luiz'),
	('guilherme.souza@gmail.com', 794133, 'Guilhermede Souza'),
	('analopez@hotmail.com', 824530, 'Ana Luiza Lopes'),
	('ada.lima@gmail.com', 634538, 'Ada Lima'),
	('filipebarcelos@hotmail.com', 621548, 'Filipe Barcelos'),
	('luana_aragao@gmail.com', 845538, 'Luana Aragão'),
	('lali_magazine@lali.com', 435876, 'Lali Magazine'),
	('livraria@livraria.com.br', 678123, 'Livraria Livros'),
	('eletronicos@eletronicos.com', 234000, 'Eletrônica El'), 
	('comercial@comercial.com', 885876, 'Comercial Pereira'),
	('cosmeticosbia@cosmeticosbia.com.br', 228123, 'Bia Cosméticos'),
	('moveis@moveismol.com', 211000, 'Moveis MOl'),
	('Vinhosxc@hotmail.com', 400876, 'Vinhos XC'),
	('livrarialemos@gmail.com.br', 678003, 'Livraria Lemos'),
	('eletronicos123@eletronicos.com', 235500, 'Eletrônica 123'),
	('lojas@gmail.com', 499876, 'Loja da Maria');

	INSERT INTO BAIRRO
	VALUES (000123, 'Coqueiral'),
	(698623, 'Manguinhos'),
	(000666, 'Campo Grande'),
	(603203, 'Jardim América'),
	(055423, 'Jacaraipe'),
	(003130, 'Lanranjeiras'),
	(204403, 'Morada'),
	(002423, 'Mata da Praia'),
	(003323, 'Santa Cruz'),
	(130123, 'Centro'),
	(098765, 'Campinho');

	INSERT INTO MUNICIPIO
	VALUES (532066, 'Cariacica', 000666), 
	(830066, 'Viana', 204403),
	(532666, 'Vila Velha', 000123),
	(032000, 'Santa Tereza', 204403),
	(100066, 'Vitória', 002423),
	(738886, 'Marechal Floriano', 003323),
	(123466, 'Domingos Martins', 098765),
	(532088, 'Serra', 698623),
	(112776, 'Aracruz', 003323),
	(532444, 'Fundão', 130123);

	INSERT INTO LOGRADOURO
	VALUES (081, 'Rua'),
	(008, 'Avenida'),
	(090, 'Rodovia'),
	(001, 'Ponte'),
	(022, 'Beco'),
	(011, 'Ferrovia'),
	(485, 'Condominio'),
	(030, 'Escada'),
	(031, 'Estrada'),
	(036, 'Reta');

	INSERT INTO ENDERECO
	VALUES ('rua', 1234565, 532066, 081),                           
	('rua', 1131515, 830066, 081),
	('avenida', 0034565, 532666, 008),
	('rodovia', 1224565, 032000, 090),
	('escada', 1234465, 100066, 030),
	('estrada', 1234555, 123466, 031),
	('rua', 3235585, 532088, 081),
	('avenida', 7234765, 532666, 081),
	('rua', 0230565, 100066, 081),
	('rua', 1236566, 100066, 081);

	INSERT INTO BOLETIM
	VALUES ('2018/06/30', '15:43:43', 9875632, 1, 2, 1234565, 194538),
	('2018/06/28', '15:50:00', 2987632, 1, 1, 1131515, 785632),
	('2016/08/02', '17:21:12', 6375212, 2, 5, 1131515, 987438),
	('2018/06/30', '13:43:32', 2375032, 1, 8, 0034565, 198500),
	('2018/07/26', '09:52:00', 6300632, 2, 4, 3235585, 693238),
	('2017/03/13', '08:00:09', 1000332, 1, 4, 1234555, 794133),
	('2018/01/25', '10:00:52', 8635632, 1, 9, 1234465, 824530),
	('2017/06/30', '19:10:47', 9870232, 1, 7, 1236566, 824530),
	('2018/09/17', '18:30:20', 9878432, 2, 5, 7234765, 634538),
	('2018/09/27', '14:00:00', 6307896, 1, 6, 0230565, 621548);

	INSERT INTO FISICA
	VALUES('F', '12345678901', 194538),
	('F', '11315618911', 785632),
	('M', '22325628902', 198500),
	('F', '32343673901', 987438),
	('M', '72545978101', 693238),
	('M', '14345618901', 794133),
	('M', '92045618904', 824530),
	('F', '72385618901', 634538),
	('F', '12645078902', 845538);

	INSERT INTO JURIDICA
	VALUES ('67362129000110', 435876),
	('67262729000112', 678123),
	('47362129000113', 234000),
	('65362529000115', 885876),
	('77362169000160', 228123),
	('77372129000170', 211000),
	('97362129000199', 400876),
	('67369199000110', 678003),
	('87368129000118', 235500),
	('57365129000115', 499876);

	INSERT INTO CLIENTE
	VALUES ('abc123**', 435876),
	('cde123**', 678123),
	('22g-3', 234000),
	('fh(2)', 885876),
	('12_dGb', 211000),
	('568hh', 845538),
	('abc123&', 634538),
	('@gh*1', 794133),
	('123456', 693238),
	('gt5tu1', 194538);

	INSERT INTO TIPO_ROUBO
	VALUES ('Roubo', 1, 9875632),
	('Furto', 2, 6375212);

	INSERT INTO ITEM_ROUBO
	VALUES ('Mochila', 1, 2987632),
	('Celular', 2, 9875632),
	('Carro', 4, 6300632),
	('Bicicleta', 5, 6375212),
	('Carteira', 6, 6307896),
	('Joia', 7, 9870232),
	('Motocicleta', 8, 2375032),
	('Dinheiro', 9, 8635632);

	INSERT INTO TIPO_DE_CONTATO
	VALUES (22, 'Telefone pessoal'),
	(33, 'Celular pessoal'),
	(34, 'Celular comercial'),
	(45, 'Telefone comercial');

	INSERT INTO CONTATO
	VALUES (33312356, 785632, 22),
	(990867754, 198500, 33),
	(991234567, 987438, 33),
	(999234567, 794133, 33),
	(33215678, 824530, 22),
	(32098765, 634538, 22),
	(33781234, 621548, 45),
	(33320987, 499876, 45),
	(970987654, 235500, 34),
	(999768032, 885876, 34);

	INSERT INTO ENTREGA
	VALUES (785632, 1234565, 'Cariacica', 22567),
	(198500, 0034565, 'Vila Velha', 90567),
	(987438, 1234465, 'Vitória', 21260),
	(794133, 3235585, 'Serra', 33569),
	(634538, 1131515, 'Viana', 42761),
	(499876, 1234565, 'Cariacica', 42509),
	(235500, 0230565, 'Vitória', 02067),
	(885876, 3235585, 'Serra', 62567);

#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
	/* EXCLUSÃO DE DADOS - DROP */

	DROP TABLE IF EXISTS usuario;
	DROP TABLE IF EXISTS cliente;
	DROP TABLE IF EXISTS municipio;
	DROP TABLE IF EXISTS bairro;
	DROP TABLE IF EXISTS endereco;
	DROP TABLE IF EXISTS boletim;
	DROP TABLE IF EXISTS entrega;


	/* MODELO FÍSICO */

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


	/* INSERÇÃO DE DADOS - INSERT */

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

>## Marco de Entrega 03 em: (27/09/18) <br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
	SELECT * FROM bairro
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/bairro.png)
	
	SELECT * FROM boletim
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/bairro.png)

	SELECT * FROM cliente
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/cliente.png)

	SELECT * FROM contato
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/contato.png)

	SELECT * FROM endereco
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/endereco.png)

	SELECT * FROM entrega
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/entrega.png)

	SELECT * FROM fisica
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/fisica.png)

	SELECT * FROM item_roubo
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/item_roubo.png)

	SELECT * FROM juridica
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/juridica.png)

	SELECT * FROM logradouro
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/logradouro.png)

	SELECT * FROM municipio
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/municipio.png)

	SELECT * FROM pessoa
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/pessoa.png)

	SELECT * FROM tipo_de_contato
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/tipo_de_contato.png)

	SELECT * FROM tipo_roubo
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/tipo_roubo.png)

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


