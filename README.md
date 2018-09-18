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
        
![Alt text](https://raw.githubusercontent.com/controlederotas/trab01/master/images/modelo_conceitual_rotas.png)
        
    
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: [Nomes dos que participaram na avaliação]
    [Grupo02]: [Nomes dos que participaram na avaliação]

#### 5.2 DECISÕES DE PROJETO

a) Traçar rotas : Inicialmente, nosso projeto visava traçar a melhor rota com base no índice de criminalidade do ponto de saída da mercadoria ao ponto de seu ponto de chegada com base no índice de criminalidade em certos pontos desta rota. Junto ao professor e, dada a dificuldade encontrada para implementar o sistema que calculasse a melhor rota, decidimos que o sistema passaria a indicar pontos de maior e menor risco para o condutor, retirando a funcionalidade de cálculo de rotas.

b) Incluir boletim de ocorrência : Consideramos que uma forma dinâmica de manter nosso banco sempre atualizado seria dar ao usuário a possibilidade de registrar assaltos sofridos.

c) Coleta de dados de tabelas já existentes : Julgamos importante a coleta de dados vindo de diversas fontes abertas e confiáveis. Estas fontes alimentarão nosso banco e servirão de base para nosso banco de dados. Utilizaremos ferramentas já conhecidas para extrair estes dados. 




>## Marco de Entrega 02 em: (13/09/2018)<br>
#### 5.3 DESCRIÇÃO DOS DADOS 
    [objeto]: [descrição do objeto]
    
    EXEMPLO:
    CLIENTE: Tabela que armazena as informações relativas ao cliente<br>
    CPF: campo que armazena o número de Cadastro de Pessoa Física para cada cliente da empresa.<br>


### 6	MODELO LÓGICO<br>
        a) inclusão do modelo lógico do banco de dados
        b) verificação de correspondencia com o modelo conceitual 
        (não serão aceitos modelos que não estejam em conformidade)

### 7	MODELO FÍSICO<br>
        a) inclusão das instruções de criacão das estruturas DDL 
        (criação de tabelas, alterações, etc..)          
        
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
        a) inclusão das instruções de inserção dos dados nas tabelas criadas pelo script de modelo físico 
        b) formato .SQL

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELAS E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script 
        (create para tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL
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


