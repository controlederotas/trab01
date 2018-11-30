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

O sistema proposto para a Controle de Rotas funcionará da seguinte forma. Exite uma pessoa, que poderá ser definida em três tipos: física, jurídica e cliente. O cliente poderá ser tanto a pessoa física quanto a jurídica. A pessoa registra um endereço para a entrega da mercadoria. Esse endereço possui um tipo de logradouro, município e um bairro. A pessoa também possuirá um contato que será classificado em diversos tipos, tais como telefone, celular, redes sociais, etc. O sistema também proporciona que o usuário insira boletins sendo ele pessoa física ou jurídica, indicando detalhes sobre o roubo. Ele será alimentado tanto pelo registro de boletins dos usuários quanto pela extração de informações de ocorrências baseadas em fontes seguras. Para registrar essa ocorrência, o usuário precisa fazer o login com email e senha. A partir dai, informará o local da ocorrência, tipo de roubo, itens roubados, sexo, data e hora. Assim, o sistema conseguirá fornecer pontos de maior índice de violência, determinando os bairros mais perigosos e então informando rotas alternativas para uma entrega de mercadoria.  Por meio de toda essa avaliação o sistema consegue mostrar ao usuário os pontos mais violentos desse percurso para que assim ele possa evitá-los.

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

    •PESSOA: Tabela que armazena informações relativas ao usuário.
    
    	-NOME: Campo que armazena o nome de uma pessoa, podendo esta ser um cliente ou não.
    	-EMAIL: Campo que armazena o email referente ao usuário.
      	-COD_USUARIO: Campo que armazena o código único do usuário.
    
    •BOLETIM: Tabela que armazena informações sobre boletins de ocorrência registrados.
    
     	-DATA_ROUBO: Indica a data do roubo registrado no boletim.
      	-HORA_ROUBO: Indica a hora do roubo registrado no boletim.
      	-TIPO_ROUBO: Indica o tipo de roubo.
      	-COD_BOLETIM: Indica o código único do boletim.
      	-ID: Chave primária que indica o código de usuário, relacionando o boletim com o usuário que o fez.
	-FK_ENDERECO_Cod: Chave estrangeira associada a um código de endereço.
	-FK_PESSOA_ID: Chave estrangeira associada a um ID de uma pessoa previamente cadastrada. 
    
    •ENTREGA: Tabela que contém informações a respeito da entrega.
    
    	-COD_ENTREGA: Campo que indica o código único referente à entrega.
      	-Destino_entrega: Campo que referencia ao código de endereço da origem da entrega. (Chave primária)
	-FK_PESSOA_ID: Chave estrangeira do ID de uma pessoa.
	-FK_ENDERECO_Cod: Chave estrangeira referente ao código de um endereço.
    
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
	- FK_PESSOA_ID_SERIAL: Chave estrangeira do ID específico de uma pessoa cadastrada no sistema.

    •JURÍDICA: Tabela que guarda informações do tipo pessoa jurídica.
    
    	- CNPJ: Campo que guarda o CNPJ de uma pessoa jurídica.
	- FK_PESSOA_ID: Chave estrangeira referente ao ID de uma pessoa cadastrada na tabela 'PESSOA'.
	
    •CLIENTE: Tabela que guarda informações relevantes ao cliente.
    
    	- Senha: Campo que armazena a senha de um cliente.
	- FK_PESSOA_ID: Chave estrangeira referente ao ID de uma pessoa cadastrada na tabela 'PESSOA'.

    •ENDERECO: Tabela que armazena endereços.
    
      -Tipo_logradouro: Campo que armazena o tipo de logradouro referente a um endereço(Rua, avenida...).
      -Cod_end: Chave primária com o código único de um endereço específico.
      -FK_MUNICIPIO_Cod_Municipio: Chave estrangeira que resgata o código que serve como chave primária de um endereço.
      -FK_Logradouro_Cod_logradouro: Chave estrangeira que resgata o código que serve como chave primária de um logradouro. 
    
    •MUNICIPIO: Tabela que armazena os municípios.
    
      -NOME_MUNICIPIO: Campo que armazena o nome do município.
      -COD_MUNICIPIO: Campo que contém o código único do município.
      -FK_BAIRRO_Cod_bairro: Chave estrangeira referente ao código de bairro da tabela 'BAIRRO'.	
      
    •BAIRRO: Tabela que armazena os bairros.
    
      -NOME_BAIRRO: Campo que armazena o nome dos bairros.
      -COD_BAIRRO: Chave primária que contém o código único do bairro.
      
    •CONTATO: Tabela que armazena um contato de um usuário.
    
    	- Contato_cliente: Campo que armazena uma forma de contato ao cliente.
	- FK_PESSOA_ID: Chave estrangeira que se refere ao ID de uma pessoa.
	- FK_TIPO_DE_CONTATO: Chave estrangeira referente ao código de um tipo de contato.
	
    •TIPO_DE_CONTATO: Tabela que armazena os tipos de contato.
    
   	- Tipo_contato: Campo que armazena os tipos de contato possíveis. 
	- Cod_tipo_contato: Chave primária que armazena o código do tipo de contato do cliente.
	
    •TIPO_ROUBO: Tabela contendo os tipos de roubo possíveis. Será útil pois o tipo de roubo é relevante para levantamento de dados mais consistentes que serão utilizados no sistema.
    
    	-Tipo: Campo que armazena o tipo de roubo.
	-Cod_tipo: Chave primária que armazena o código de um tipo específico de roubo.
	-FK_BOLETIM_ID: Chave estrangeira que faz referência ao ID do boletim.
	
    •ITEM_ROUBO: Tabela contendo os itens, especificamente, que foram roubados.
    
    	-Item: Campo que armazena o nome do item roubado. 
	-Cod_Item: Chave primária para identificar o item.
	-FK_BOLETIM_ID: Chave estrangeira que faz referência ao ID do boletim.
	
    •LOGRADOURO: Tabela contendo informações sobre logradouros e seus possíveis tipos.
    
    	-Cod_logradouro: Chave primária identificando o código do logradouro.
	-Tipo_logradouro: Campo que armazena o tipo de logradouro.

    •
	
    


### 6	MODELO LÓGICO<br>

![Alt text](https://raw.githubusercontent.com/controlederotas/trab01/master/images/modelo_logico.png)

### 7	MODELO FÍSICO<br>

	CREATE TABLE PESSOA (
	    ID SERIAL PRIMARY KEY,
	    Nome VARCHAR(100)
	);

	CREATE TABLE ENDERECO (
	    Tipo_logradouro VARCHAR(50),
	    Cod_end INT PRIMARY KEY,
	    FK_BAIRRO_Cod_bairro INT,
	    FK_Logradouro_Cod_logradouro INT
	);

	CREATE TABLE MUNICIPIO (
	    Nome_municipio VARCHAR(50),
	    Cod_municipio INT PRIMARY KEY
	);

	CREATE TABLE BOLETIM (
	    Data_roubo DATE,
	    Hora_roubo TIME,
	    ID INT PRIMARY KEY,
	    FK_TIPO_ROUBO_Cod_tipo INT,
	    FK_ENDERECO_Cod_end INT,
	    FK_PESSOA_ID SERIAL
	);

	CREATE TABLE BAIRRO (
	    Nome_bairro VARCHAR(80),
	    Cod_bairro INT PRIMARY KEY,
	    FK_MUNICIPIO_Cod_municipio INT
	);

	CREATE TABLE FISICA (
	    Sexo CHAR(1),
	    CPF VARCHAR(15),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE JURIDICA (
	    CNPJ VARCHAR(50),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE CLIENTE (
	    Senha VARCHAR(20),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE TIPO_ROUBO (
	    Tipo VARCHAR(50),
	    Cod_tipo INT PRIMARY KEY
	);

	CREATE TABLE ITEM_ROUBO (
	    Item VARCHAR(50),
	    Cod_item INT PRIMARY KEY
	);

	CREATE TABLE Logradouro (
	    Cod_logradouro INT PRIMARY KEY,
	    Tipo_logradouro VARCHAR(50)
	);

	CREATE TABLE CONTATO (
	    Contato_cliente VARCHAR(50),
	    FK_PESSOA_ID SERIAL,
	    FK_TIPO_DE_CONTATO_Cod_tipo_contato INT
	);

	CREATE TABLE TIPO_DE_CONTATO (
	    Cod_tipo_contato INT PRIMARY KEY,
	    Tipo_contato VARCHAR(50)
	);

	CREATE TABLE Possui (
	    FK_BOLETIM_ID INT,
	    FK_ITEM_ROUBO_Cod_item INT
	);

	CREATE TABLE ENTREGA (
	    FK_ENDERECO_Cod_end INT,
	    FK_CLIENTE_FK_PESSOA_ID SERIAL,
	    Cod_entrega INT PRIMARY KEY,
	    cod_origem INT,
	    cod_destino INT
	);

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_1
	    FOREIGN KEY (FK_BAIRRO_Cod_bairro)
	    REFERENCES BAIRRO (Cod_bairro)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_2
	    FOREIGN KEY (FK_Logradouro_Cod_logradouro)
	    REFERENCES Logradouro (Cod_logradouro)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_1
	    FOREIGN KEY (FK_TIPO_ROUBO_Cod_tipo)
	    REFERENCES TIPO_ROUBO (Cod_tipo)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_2
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_3
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BAIRRO ADD CONSTRAINT FK_BAIRRO_1
	    FOREIGN KEY (FK_MUNICIPIO_Cod_municipio)
	    REFERENCES MUNICIPIO (Cod_municipio)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE FISICA ADD CONSTRAINT FK_FISICA_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE JURIDICA ADD CONSTRAINT FK_JURIDICA_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE CLIENTE ADD CONSTRAINT FK_CLIENTE_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_0
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_1
	    FOREIGN KEY (FK_TIPO_DE_CONTATO_Cod_tipo_contato)
	    REFERENCES TIPO_DE_CONTATO (Cod_tipo_contato)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE Possui ADD CONSTRAINT FK_Possui_0
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE Possui ADD CONSTRAINT FK_Possui_1
	    FOREIGN KEY (FK_ITEM_ROUBO_Cod_item)
	    REFERENCES ITEM_ROUBO (Cod_item)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_1
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_2
	    FOREIGN KEY (FK_CLIENTE_FK_PESSOA_ID)
	    REFERENCES CLIENTE (FK_PESSOA_ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;	


### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
	INSERT INTO PESSOA
	VALUES (194538, 'Patricia Lima'),
	(785632, 'Luciana Fernandes'),
	(198500,  'Pablo Rodrigues'),
	(987438, 'Rodrigo Xavier'),
	(693238,  'José Luiz'),
	(794133, 'Guilhermede Souza'),
	(824530, 'Ana Luiza Lopes'),
	(634538, 'Ada Lima'),
	(621548, 'Filipe Barcelos'),
	(845538, 'Luana Aragão'),
	(435876, 'Lali Magazine'),
	(678123, 'Livraria Livros'),
	(234000, 'Eletrônica El'), 
	(885876, 'Comercial Pereira'),
	(228123, 'Bia Cosméticos'),
	(211000, 'Moveis MOl'),
	(400876, 'Vinhos XC'),
	(678003, 'Livraria Lemos'),
	(235500, 'Eletrônica 123'),
	(499876, 'Loja da Maria');

	INSERT INTO MUNICIPIO
	VALUES ('Cariacica', 532066), 
	('Viana', 830066),
	('Vila Velha', 532666),
	('Santa Tereza', 032000),
	('Vitória', 100066),
	('Marechal Floriano', 738886),
	('Domingos Martins', 123466),
	('Serra', 532088),
	('Aracruz', 112776),
	('Fundão', 532444);

	INSERT INTO BAIRRO
	VALUES ('Coqueiral', 000123, 532666),
	('Manguinhos', 698623, 532088),
	('Campo Grande', 000666, 532066),
	('Jardim América', 603203, 532066),
	('Jacaraipe', 055423, 532088),
	('Lanranjeiras', 003130, 532088),
	('Morada', 204403, 532444),
	('Mata da Praia', 002423, 100066),
	('Santa Cruz', 003323, 112776),
	('Centro', 130123, 100066),
	('Campinho', 098765, 123466);

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
	VALUES ('rua', 1234565, 000123, 081),                           
	('rua', 1131515, 698623, 081),
	('avenida', 0034565, 000666, 008),
	('rodovia', 1224565, 003130, 090),
	('escada', 1234465, 130123, 030),
	('estrada', 1234555, 098765, 031),
	('rua', 3235585, 000666, 081),
	('avenida', 7234765, 003323, 081),
	('rua', 0230565, 603203, 081),
	('rua', 1236566, 002423, 081);

	INSERT INTO TIPO_ROUBO
	VALUES ('Roubo', 1),
	('Furto', 2);

	INSERT INTO BOLETIM
	VALUES ('2018/06/30', '15:43:43', 9875632, 1, 1234565, 194538),
	('2018/06/28', '15:50:00', 2987632, 1, 1234565, 785632),
	('2016/08/02', '17:21:12', 6375212, 2, 7234765, 785632),
	('2018/06/30', '13:43:32', 2375032, 1, 3235585, 198500),
	('2018/07/26', '09:52:00', 6300632, 2, 7234765, 794133),
	('2017/03/13', '08:00:09', 1000332, 1, 7234765, 824530),
	('2018/01/25', '10:00:52', 8635632, 1, 0230565, 693238),
	('2017/06/30', '19:10:47', 9870232, 1, 0230565, 845538),
	('2018/09/17', '18:30:20', 9878432, 2, 1234565, 634538),
	('2018/09/27', '14:00:00', 6307896, 1, 1234565, 621548);

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

	INSERT INTO ITEM_ROUBO
	VALUES ('Mochila', 11),
	('Celular', 22),
	('Carro', 44),
	('Bicicleta', 55),
	('Carteira', 66),
	('Joia', 77),
	('Motocicleta', 88),
	('Dinheiro', 99);

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
	VALUES (1234565, 435876, 0067, 997, 900),
	(1131515, 678123, 9045, 90567, 776),
	(1131515, 678123, 2211, 21260, 977),
	(0034565, 885876, 5689, 33569, 214),
	(3235585, 211000, 0955, 42761, 657),
	(0230565, 845538, 1145, 42509, 768),
	(1236566, 794133, 7800, 02067, 900),
	(1236566, 194538, 4399, 62567, 970);

	INSERT INTO possui
	VALUES (9875632, 11),
	(2987632, 22),
	(6375212, 44),
	(6375212, 22),
	(1000332, 66),
	(1000332, 99),
	(1000332, 22),
	(6307896, 55);
	
#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELAS E INSERÇÃO DOS DADOS
	CREATE TABLE PESSOA (
	    ID SERIAL PRIMARY KEY,
	    Nome VARCHAR(100)
	);

	CREATE TABLE ENDERECO (
	    Tipo_logradouro VARCHAR(50),
	    Cod_end INT PRIMARY KEY,
	    FK_BAIRRO_Cod_bairro INT,
	    FK_Logradouro_Cod_logradouro INT
	);

	CREATE TABLE MUNICIPIO (
	    Nome_municipio VARCHAR(50),
	    Cod_municipio INT PRIMARY KEY
	);

	CREATE TABLE BOLETIM (
	    Data_roubo DATE,
	    Hora_roubo TIME,
	    ID INT PRIMARY KEY,
	    FK_TIPO_ROUBO_Cod_tipo INT,
	    FK_ENDERECO_Cod_end INT,
	    FK_PESSOA_ID SERIAL
	);

	CREATE TABLE BAIRRO (
	    Nome_bairro VARCHAR(80),
	    Cod_bairro INT PRIMARY KEY,
	    FK_MUNICIPIO_Cod_municipio INT
	);

	CREATE TABLE FISICA (
	    Sexo CHAR(1),
	    CPF VARCHAR(15),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE JURIDICA (
	    CNPJ VARCHAR(50),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE CLIENTE (
	    Senha VARCHAR(20),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE TIPO_ROUBO (
	    Tipo VARCHAR(50),
	    Cod_tipo INT PRIMARY KEY
	);

	CREATE TABLE ITEM_ROUBO (
	    Item VARCHAR(50),
	    Cod_item INT PRIMARY KEY
	);

	CREATE TABLE Logradouro (
	    Cod_logradouro INT PRIMARY KEY,
	    Tipo_logradouro VARCHAR(50)
	);

	CREATE TABLE CONTATO (
	    Contato_cliente VARCHAR(50),
	    FK_PESSOA_ID SERIAL,
	    FK_TIPO_DE_CONTATO_Cod_tipo_contato INT
	);

	CREATE TABLE TIPO_DE_CONTATO (
	    Cod_tipo_contato INT PRIMARY KEY,
	    Tipo_contato VARCHAR(50)
	);

	CREATE TABLE Possui (
	    FK_BOLETIM_ID INT,
	    FK_ITEM_ROUBO_Cod_item INT
	);

	CREATE TABLE ENTREGA (
	    FK_ENDERECO_Cod_end INT,
	    FK_CLIENTE_FK_PESSOA_ID SERIAL,
	    Cod_entrega INT PRIMARY KEY,
	    cod_origem INT,
	    cod_destino INT
	);

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_1
	    FOREIGN KEY (FK_BAIRRO_Cod_bairro)
	    REFERENCES BAIRRO (Cod_bairro)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_2
	    FOREIGN KEY (FK_Logradouro_Cod_logradouro)
	    REFERENCES Logradouro (Cod_logradouro)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_1
	    FOREIGN KEY (FK_TIPO_ROUBO_Cod_tipo)
	    REFERENCES TIPO_ROUBO (Cod_tipo)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_2
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_3
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BAIRRO ADD CONSTRAINT FK_BAIRRO_1
	    FOREIGN KEY (FK_MUNICIPIO_Cod_municipio)
	    REFERENCES MUNICIPIO (Cod_municipio)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE FISICA ADD CONSTRAINT FK_FISICA_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE JURIDICA ADD CONSTRAINT FK_JURIDICA_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE CLIENTE ADD CONSTRAINT FK_CLIENTE_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_0
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_1
	    FOREIGN KEY (FK_TIPO_DE_CONTATO_Cod_tipo_contato)
	    REFERENCES TIPO_DE_CONTATO (Cod_tipo_contato)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE Possui ADD CONSTRAINT FK_Possui_0
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE Possui ADD CONSTRAINT FK_Possui_1
	    FOREIGN KEY (FK_ITEM_ROUBO_Cod_item)
	    REFERENCES ITEM_ROUBO (Cod_item)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_1
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_2
	    FOREIGN KEY (FK_CLIENTE_FK_PESSOA_ID)
	    REFERENCES CLIENTE (FK_PESSOA_ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;	

	
	/* Inserção dos dados */
	
	INSERT INTO PESSOA
	VALUES (194538, 'Patricia Lima'),
	(785632, 'Luciana Fernandes'),
	(198500,  'Pablo Rodrigues'),
	(987438, 'Rodrigo Xavier'),
	(693238,  'José Luiz'),
	(794133, 'Guilhermede Souza'),
	(824530, 'Ana Luiza Lopes'),
	(634538, 'Ada Lima'),
	(621548, 'Filipe Barcelos'),
	(845538, 'Luana Aragão'),
	(435876, 'Lali Magazine'),
	(678123, 'Livraria Livros'),
	(234000, 'Eletrônica El'), 
	(885876, 'Comercial Pereira'),
	(228123, 'Bia Cosméticos'),
	(211000, 'Moveis MOl'),
	(400876, 'Vinhos XC'),
	(678003, 'Livraria Lemos'),
	(235500, 'Eletrônica 123'),
	(499876, 'Loja da Maria');

	INSERT INTO MUNICIPIO
	VALUES ('Cariacica', 532066), 
	('Viana', 830066),
	('Vila Velha', 532666),
	('Santa Tereza', 032000),
	('Vitória', 100066),
	('Marechal Floriano', 738886),
	('Domingos Martins', 123466),
	('Serra', 532088),
	('Aracruz', 112776),
	('Fundão', 532444);

	INSERT INTO BAIRRO
	VALUES ('Coqueiral', 000123, 532666),
	('Manguinhos', 698623, 532088),
	('Campo Grande', 000666, 532066),
	('Jardim América', 603203, 532066),
	('Jacaraipe', 055423, 532088),
	('Lanranjeiras', 003130, 532088),
	('Morada', 204403, 532444),
	('Mata da Praia', 002423, 100066),
	('Santa Cruz', 003323, 112776),
	('Centro', 130123, 100066),
	('Campinho', 098765, 123466);

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
	VALUES ('rua', 1234565, 000123, 081),                           
	('rua', 1131515, 698623, 081),
	('avenida', 0034565, 000666, 008),
	('rodovia', 1224565, 003130, 090),
	('escada', 1234465, 130123, 030),
	('estrada', 1234555, 098765, 031),
	('rua', 3235585, 000666, 081),
	('avenida', 7234765, 003323, 081),
	('rua', 0230565, 603203, 081),
	('rua', 1236566, 002423, 081);

	INSERT INTO TIPO_ROUBO
	VALUES ('Roubo', 1),
	('Furto', 2);

	INSERT INTO BOLETIM
	VALUES ('2018/06/30', '15:43:43', 9875632, 1, 1234565, 194538),
	('2018/06/28', '15:50:00', 2987632, 1, 1234565, 785632),
	('2016/08/02', '17:21:12', 6375212, 2, 7234765, 785632),
	('2018/06/30', '13:43:32', 2375032, 1, 3235585, 198500),
	('2018/07/26', '09:52:00', 6300632, 2, 7234765, 794133),
	('2017/03/13', '08:00:09', 1000332, 1, 7234765, 824530),
	('2018/01/25', '10:00:52', 8635632, 1, 0230565, 693238),
	('2017/06/30', '19:10:47', 9870232, 1, 0230565, 845538),
	('2018/09/17', '18:30:20', 9878432, 2, 1234565, 634538),
	('2018/09/27', '14:00:00', 6307896, 1, 1234565, 621548);

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

	INSERT INTO ITEM_ROUBO
	VALUES ('Mochila', 11),
	('Celular', 22),
	('Carro', 44),
	('Bicicleta', 55),
	('Carteira', 66),
	('Joia', 77),
	('Motocicleta', 88),
	('Dinheiro', 99);

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
	VALUES (1234565, 435876, 0067, 997, 900),
	(1131515, 678123, 9045, 90567, 776),
	(1131515, 678123, 2211, 21260, 977),
	(0034565, 885876, 5689, 33569, 214),
	(3235585, 211000, 0955, 42761, 657),
	(0230565, 845538, 1145, 42509, 768),
	(1236566, 794133, 7800, 02067, 900),
	(1236566, 194538, 4399, 62567, 970);

	INSERT INTO possui
	VALUES (9875632, 11),
	(2987632, 22),
	(6375212, 44),
	(6375212, 22),
	(1000332, 66),
	(1000332, 99),
	(1000332, 22),
	(6307896, 55);

#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
	/* EXCLUSÃO DE DADOS - DROP */


	/* MODELO FÍSICO */

		CREATE TABLE PESSOA (
	    ID SERIAL PRIMARY KEY,
	    Nome VARCHAR(100)
	);

	CREATE TABLE ENDERECO (
	    Tipo_logradouro VARCHAR(50),
	    Cod_end INT PRIMARY KEY,
	    FK_BAIRRO_Cod_bairro INT,
	    FK_Logradouro_Cod_logradouro INT
	);

	CREATE TABLE MUNICIPIO (
	    Nome_municipio VARCHAR(50),
	    Cod_municipio INT PRIMARY KEY
	);

	CREATE TABLE BOLETIM (
	    Data_roubo DATE,
	    Hora_roubo TIME,
	    ID INT PRIMARY KEY,
	    FK_TIPO_ROUBO_Cod_tipo INT,
	    FK_ENDERECO_Cod_end INT,
	    FK_PESSOA_ID SERIAL
	);

	CREATE TABLE BAIRRO (
	    Nome_bairro VARCHAR(80),
	    Cod_bairro INT PRIMARY KEY,
	    FK_MUNICIPIO_Cod_municipio INT
	);

	CREATE TABLE FISICA (
	    Sexo CHAR(1),
	    CPF VARCHAR(15),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE JURIDICA (
	    CNPJ VARCHAR(50),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE CLIENTE (
	    Senha VARCHAR(20),
	    FK_PESSOA_ID SERIAL PRIMARY KEY
	);

	CREATE TABLE TIPO_ROUBO (
	    Tipo VARCHAR(50),
	    Cod_tipo INT PRIMARY KEY
	);

	CREATE TABLE ITEM_ROUBO (
	    Item VARCHAR(50),
	    Cod_item INT PRIMARY KEY
	);

	CREATE TABLE Logradouro (
	    Cod_logradouro INT PRIMARY KEY,
	    Tipo_logradouro VARCHAR(50)
	);

	CREATE TABLE CONTATO (
	    Contato_cliente VARCHAR(50),
	    FK_PESSOA_ID SERIAL,
	    FK_TIPO_DE_CONTATO_Cod_tipo_contato INT
	);

	CREATE TABLE TIPO_DE_CONTATO (
	    Cod_tipo_contato INT PRIMARY KEY,
	    Tipo_contato VARCHAR(50)
	);

	CREATE TABLE Possui (
	    FK_BOLETIM_ID INT,
	    FK_ITEM_ROUBO_Cod_item INT
	);

	CREATE TABLE ENTREGA (
	    FK_ENDERECO_Cod_end INT,
	    FK_CLIENTE_FK_PESSOA_ID SERIAL,
	    Cod_entrega INT PRIMARY KEY,
	    cod_origem INT,
	    cod_destino INT
	);

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_1
	    FOREIGN KEY (FK_BAIRRO_Cod_bairro)
	    REFERENCES BAIRRO (Cod_bairro)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENDERECO ADD CONSTRAINT FK_ENDERECO_2
	    FOREIGN KEY (FK_Logradouro_Cod_logradouro)
	    REFERENCES Logradouro (Cod_logradouro)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_1
	    FOREIGN KEY (FK_TIPO_ROUBO_Cod_tipo)
	    REFERENCES TIPO_ROUBO (Cod_tipo)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_2
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE BOLETIM ADD CONSTRAINT FK_BOLETIM_3
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE BAIRRO ADD CONSTRAINT FK_BAIRRO_1
	    FOREIGN KEY (FK_MUNICIPIO_Cod_municipio)
	    REFERENCES MUNICIPIO (Cod_municipio)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE FISICA ADD CONSTRAINT FK_FISICA_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE JURIDICA ADD CONSTRAINT FK_JURIDICA_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE CLIENTE ADD CONSTRAINT FK_CLIENTE_1
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_0
	    FOREIGN KEY (FK_PESSOA_ID)
	    REFERENCES PESSOA (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_1
	    FOREIGN KEY (FK_TIPO_DE_CONTATO_Cod_tipo_contato)
	    REFERENCES TIPO_DE_CONTATO (Cod_tipo_contato)
	    ON DELETE CASCADE ON UPDATE CASCADE;

	ALTER TABLE Possui ADD CONSTRAINT FK_Possui_0
	    FOREIGN KEY (FK_BOLETIM_ID)
	    REFERENCES BOLETIM (ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE Possui ADD CONSTRAINT FK_Possui_1
	    FOREIGN KEY (FK_ITEM_ROUBO_Cod_item)
	    REFERENCES ITEM_ROUBO (Cod_item)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_1
	    FOREIGN KEY (FK_ENDERECO_Cod_end)
	    REFERENCES ENDERECO (Cod_end)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;

	ALTER TABLE ENTREGA ADD CONSTRAINT FK_ENTREGA_2
	    FOREIGN KEY (FK_CLIENTE_FK_PESSOA_ID)
	    REFERENCES CLIENTE (FK_PESSOA_ID)
	    ON DELETE RESTRICT ON UPDATE RESTRICT;	

	
	/* Inserção dos dados */
	
	INSERT INTO PESSOA
	VALUES (194538, 'Patricia Lima'),
	(785632, 'Luciana Fernandes'),
	(198500,  'Pablo Rodrigues'),
	(987438, 'Rodrigo Xavier'),
	(693238,  'José Luiz'),
	(794133, 'Guilhermede Souza'),
	(824530, 'Ana Luiza Lopes'),
	(634538, 'Ada Lima'),
	(621548, 'Filipe Barcelos'),
	(845538, 'Luana Aragão'),
	(435876, 'Lali Magazine'),
	(678123, 'Livraria Livros'),
	(234000, 'Eletrônica El'), 
	(885876, 'Comercial Pereira'),
	(228123, 'Bia Cosméticos'),
	(211000, 'Moveis MOl'),
	(400876, 'Vinhos XC'),
	(678003, 'Livraria Lemos'),
	(235500, 'Eletrônica 123'),
	(499876, 'Loja da Maria');

	INSERT INTO MUNICIPIO
	VALUES ('Cariacica', 532066), 
	('Viana', 830066),
	('Vila Velha', 532666),
	('Santa Tereza', 032000),
	('Vitória', 100066),
	('Marechal Floriano', 738886),
	('Domingos Martins', 123466),
	('Serra', 532088),
	('Aracruz', 112776),
	('Fundão', 532444);

	INSERT INTO BAIRRO
	VALUES ('Coqueiral', 000123, 532666),
	('Manguinhos', 698623, 532088),
	('Campo Grande', 000666, 532066),
	('Jardim América', 603203, 532066),
	('Jacaraipe', 055423, 532088),
	('Lanranjeiras', 003130, 532088),
	('Morada', 204403, 532444),
	('Mata da Praia', 002423, 100066),
	('Santa Cruz', 003323, 112776),
	('Centro', 130123, 100066),
	('Campinho', 098765, 123466);

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
	VALUES ('rua', 1234565, 000123, 081),                           
	('rua', 1131515, 698623, 081),
	('avenida', 0034565, 000666, 008),
	('rodovia', 1224565, 003130, 090),
	('escada', 1234465, 130123, 030),
	('estrada', 1234555, 098765, 031),
	('rua', 3235585, 000666, 081),
	('avenida', 7234765, 003323, 081),
	('rua', 0230565, 603203, 081),
	('rua', 1236566, 002423, 081);

	INSERT INTO TIPO_ROUBO
	VALUES ('Roubo', 1),
	('Furto', 2);

	INSERT INTO BOLETIM
	VALUES ('2018/06/30', '15:43:43', 9875632, 1, 1234565, 194538),
	('2018/06/28', '15:50:00', 2987632, 1, 1234565, 785632),
	('2016/08/02', '17:21:12', 6375212, 2, 7234765, 785632),
	('2018/06/30', '13:43:32', 2375032, 1, 3235585, 198500),
	('2018/07/26', '09:52:00', 6300632, 2, 7234765, 794133),
	('2017/03/13', '08:00:09', 1000332, 1, 7234765, 824530),
	('2018/01/25', '10:00:52', 8635632, 1, 0230565, 693238),
	('2017/06/30', '19:10:47', 9870232, 1, 0230565, 845538),
	('2018/09/17', '18:30:20', 9878432, 2, 1234565, 634538),
	('2018/09/27', '14:00:00', 6307896, 1, 1234565, 621548);

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

	INSERT INTO ITEM_ROUBO
	VALUES ('Mochila', 11),
	('Celular', 22),
	('Carro', 44),
	('Bicicleta', 55),
	('Carteira', 66),
	('Joia', 77),
	('Motocicleta', 88),
	('Dinheiro', 99);

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
	VALUES (1234565, 435876, 0067, 997, 900),
	(1131515, 678123, 9045, 90567, 776),
	(1131515, 678123, 2211, 21260, 977),
	(0034565, 885876, 5689, 33569, 214),
	(3235585, 211000, 0955, 42761, 657),
	(0230565, 845538, 1145, 42509, 768),
	(1236566, 794133, 7800, 02067, 900),
	(1236566, 194538, 4399, 62567, 970);

	INSERT INTO possui
	VALUES (9875632, 11),
	(2987632, 22),
	(6375212, 44),
	(6375212, 22),
	(1000332, 66),
	(1000332, 99),
	(1000332, 22),
	(6307896, 55);
>## Marco de Entrega 03 em: (27/09/18) <br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
	SELECT * FROM bairro
![Alt text](https://github.com/controlederotas/trab01/blob/master/tabela_bairro.png)
	
	SELECT * FROM boletim
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/boletim.png)

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
	SELECT * FROM bairro WHERE nome_bairo = 'Campo Grande'
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/where_1.png)

	SELECT * FROM entrega WHERE destino_entrega = 'Cariacica'
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/where_2.png)

	SELECT * FROM tipo_de_contato WHERE tipo_contato = 'Celular comercial'
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/where_3.png)

	SELECT * FROM logradouro WHERE tipo_logradouro = 'Rua'
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/where_4.png)


#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
	
	SELECT * FROM tipo_de_contato WHERE cod_tipo_contato = '22' OR tipo_contato = 'Telefone Comercial';
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_1.JPG)


	select * from boletim where (current_date - data_roubo)>365;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_2.JPG)


	Select nome from pessoa inner join boletim on (pessoa.id = boletim.fk_pessoa_id);
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_3.JPG)


	SELECT * FROM endereco WHERE fk_logradouro_cod_logradouro IS NOT NULL;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_4.JPG)


	SELECT * FROM entrega WHERE cod_entrega > 42761 AND destino_entrega = 'Serra';
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_5.JPG)


	SELECT * FROM boletim WHERE cod_tipo = 1 AND cod_item > 3;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_6.JPG)


	SELECT * FROM boletim WHERE cod_item = 2 OR cod_tipo = 2;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_7.JPG)


	SELECT fk_boletim_id AS id_boletim FROM tipo_roubo;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_8.JPG)


	SELECT fk_pessoa_id AS id_pessoa FROM juridica;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.3_9.JPG)


	SELECT fk_logradouro_cod_logradouro AS cod_logradouro FROM endereco;
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/9.2_10.JPG)
    
    
    
    
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.
    
	SELECT * FROM pessoa WHERE nome LIKE 'A%';
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/like_1.png)

	SELECT * FROM pessoa WHERE nome LIKE '%s';
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/like_2.png)

	SELECT * FROM bairro WHERE nome_bairro LIKE '______';
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/like_3.png)

	SELECT * FROM bairro WHERE nome_bairro LIKE '_a%'
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/like_4.png)

	SELECT * FROM pessoa WHERE nome LIKE '%ana%';
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/like_5.png)

	SELECT id, current_date - data_roubo as "tempo em dias registro BO" FROM boletim 
![Alt text](https://github.com/controlederotas/trab01/blob/master/images/data_1.png)


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


