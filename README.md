# TRABALHO 01:  Título do Trabalho
Trabalho desenvolvido durante a disciplina de BD1

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
primeiro_componente_do_grupo:luciano.ananias.50@gmail.com<br>
segundo_componente_do_grupo:guguandrade080299@gmail.com<br>
...<br>

### 2.INTRODUÇÃO E MOTIVAÇÃO<br>

> A empresa “GL Projetos” tem como principal objetivo acelerar processos em diversas áreas, assim poupando o recurso mais caro nos dias de hoje, o tempo.
O Sistema criado pela nossa empresa visa acelerar diversas atividades e burocracias tendo em vista a utilização de um software capaz de otimizar processos como marcações de consultas, resultados de exames e evitar aglomerações em um período onde devemos ficar a maior parte do tempo dentro de nossas residências.

 

### 3.MINI-MUNDO<br>

> Um laboratório necessita de um sistema que armazene os dados dos pacientes (nome, CPF, data de nascimento, endereço e telefone) e dos funcionários (nome, registro, endereço, horário de entrada e saída) para melhor controle dos dados e eficiência da empresa. 
Cada paciente poderá fazer mais de um tipo de exames e os resultados dos mesmos deverão ser armazenados de acordo. O paciente é atendido com um funcionário que realiza o processo de coleta de sangue.
O objetivo do projeto é entregar os resultados de maneira simples, rápida e intuitiva ao paciente.

### 4.PROTOTIPAÇÃO, PERGUNTAS A SEREM RESPONDIDAS E TABELA DE DADOS<br>
#### 4.1 RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%201.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%202.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%203.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%204.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%205.png?raw=true "Title")

![Arquivo PDF do Protótipo Balsamiq](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/arquivos/Mockups.pdf?raw=true "Clínica")

#### 4.2 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
O sistema poderá contar com uma série de dados acerca de gerarem metadados para entender o processo de propagação de doenças, como principal a ser investigada, o COVID19.
```
- Relatório geral sobre a quantidade de casos positivos em uma determinada região.
- Relatório sobre a quantidade de pessoas que testam positivo em um total.
- Relatório acerca do crescimento de casos com o passar dos dias.
- Perfil das pessoas que mais testam positivo.
- Relatório sobre funcionários que testaram positivo.
```

 
 
#### 4.3 TABELA DE DADOS DO SISTEMA:
    (https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/arquivos/tabelaConsultaDadosBD.xlsx)
   
    
### 5.MODELO CONCEITUAL<br>
    
![Modelo Conceitual](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Modelo%20Conceitual.png?raw=true "Modelo Conceitual")
    
#### 5.1 Validação do Modelo Conceitual
    [PROVISÕES]: [Kelvin L.]
    [Grupo02]: [Nomes dos que participaram na avaliação]

#### 5.2 Descrição dos dados 

#### PESSOA: TABELA QUE ARMAZENA DADOS DO TIPO PESSOA DO SISTEMA.
   ```
   -ID_PESSOA: ID para identificação da pessoa.
   -ID_TELEFONE:ID para identificação do telefone.
   -ID_ENDERECO:ID para identificação do endereço.
   -NOME_PESSOA:Campo que armazena o nome da pessoa.
   -CPF:Campo que armazena o cadastro de pessoa fisica.
  ```

##### CONTATO: TABELA QUE ARMAZENA DADOS DO TIPO CONTATO NO SISTEMA
```
   -ID_TELEFONE:ID para identificação do telefone.
   -ID_PESSOA: ID para identificação da pessoa.
   -TIPO_CONTATO:Campo que armazena o tipo de contato.
   -CONTATO:Campo que armazena o contato.
```
##### ENDEREÇO: TABELA QUE ARMAZENA DADOS DO TIPO ENDEREÇO NO SISTEMA.
 ```
   -ID_ENDERECO:ID para identificação do endereço.
   -ID_PESSOA: ID para identificação da pessoa.
   -CEP:Campo que armazena o CEP.
   -NUMERO:Campo que armazena o numero referente a uma casa ou residência.
   -LOGRADOURO:Campo que armazena o logradouro.
   -TIPO_LOGRADOURO:Campo que armazena o tipo de logradouro.
```

#### PACIENTE: TABELA QUE ARMAZENA DADOS DO TIPO PACIENTE NO SISTEMA.
 ```  
   -ID_PACIENTE: ID para identificação do paciente.
   -ID_PESSOA: ID para identificação da pessoa.
 
 ```

#### AGENDA: TABELA QUE ARMAZENA DADOS DO TIPO AGENDA NO SISTEMA.
 ```  
   -ID_AGENDAMENTO: ID para identificação do agendamento.
   -ID_PACIENTE: ID para identificação do paciente.
   -ID_EXAME: ID para identificação do exame.
   -DATA_EXAME: Campo que armazena a data do exame.
 ```

#### FUNCIONARIO: TABELA QUE ARMAZENA OS DADOS DO TIPO FUNCIONARIO NO SISTEMA.
 ```
   -ID_FUNCIONARIO:ID para identificação do funcionario.
   -ID_PESSOA: ID para identificação da pessoa.
   -CARGA_HORARIO:Campo que armazena a carga horaria do funcionario.
   -TIPO_FUNCIONARIO:Campo que armazena o tipo do funcionário.
 ```

#### EXAME: TABELA QUE ARMAZENA OS DADOS DO TIPO EXAME NO SISTEMA.
 ```
   -ID_EXAME: ID para identificação do exame.
   -ID_FUNCIONARIO:ID para identificação do funcionario.
   -ID_AGENDAMENTO: ID para identificação do agendamento.
   -TIPO_EXAME:Campo que informa o tipo do exame agendado.
   -STATUS:Campo que informa o status do exame.
 ```

#### RESULTADO: TABELA QUE ARMAZENA DADOS DO TIPO RESULTADO NO SISTEMA.
 ```
   -ID_RESULTADO:ID para identificação do resultado.
   -ID_EXAME: ID para identificação do exame.
   -RESULTADO:Campo que informa o resultado do exame.
   -HORA_RESULTADO:Campo que informa a hora do resultado.
 ```





### 6	MODELO LÓGICO<br>

![Modelo Logico](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Logico.png?raw=true "Modelo Logico")

### 7	MODELO FÍSICO<br>

```
CREATE TABLE pessoa(
    id_pessoa int not null,
    id_telefone int not null,
    id_endereco int not null,
    nome_pessoa varchar(45),
    cpf int,
    PRIMARY KEY (id_pessoa)
);

CREATE TABLE contato(
    id_telefone int not null,
    tipo_contato varchar(20),
    contato varchar(50),
    PRIMARY KEY (id_telefone),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE endereco(
    id_endereco int not null,
    cep int,
    numero int,
    logradouro varchar(30),
    tipo_logradouro varchar(30),
    PRIMARY KEY (id_endereco ),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE paciente(
    id_paciente int not null,
    id_pessoa int not null,
    PRIMARY KEY (id_paciente),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE agenda(
    id_agendamento int not null,
    id_paciente int not null,
    data_exame date,
    PRIMARY KEY (id_agendamento),
    FOREIGN KEY(id_paciente) REFERENCES paciente(id_paciente)
);

CREATE TABLE funcionario(
    id_funcionario int not null,
    id_pessoa int not null,
    carga_horaria varchar(50),
    tipo_funcionario varchar(30),
    PRIMARY KEY (id_funcionario),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE exame(
    id_exame int not null,
    id_funcionario int not null,
    id_agendamento int not null,
    tipo_exame varchar(30),
    status varchar(30),
    PRIMARY KEY (id_exame),
    FOREIGN KEY(id_funcionario ) REFERENCES funcionario(id_funcionario ),
    FOREIGN KEY(id_agendamento ) REFERENCES agenda(id_agendamento )
);

CREATE TABLE resultado(
    id_resultado int not null,
    id_exame int not null,
    resultado varchar(30),
    hora_resultado date,
    PRIMARY KEY (id_resultado ),
    FOREIGN KEY(id_exame ) REFERENCES exame(id_exame )
);

ALTER TABLE pessoa ADD CONSTRAINT id_telefone FOREIGN KEY (id_telefone) REFERENCES contato(id_telefone );  
ALTER TABLE pessoa ADD CONSTRAINT id_endereco FOREIGN KEY (id_endereco ) REFERENCES endereco(id_endereco);
ALTER TABLE agenda ADD CONSTRAINT id_exame  FOREIGN KEY (id_exame) REFERENCES exame(id_exame );
```
     
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>

```
INSERT INTO contato(id_telefone, tipo_contato , contato) VALUES 
(1, 'email', 'lucianobobao@gmail.com'),
(2, 'email', 'helok@gmail.com'),
(3, 'telefone', 134815114),
(4, 'telefone', 879848455);

INSERT INTO endereco(id_endereco , cep, numero, logradouro, tipo_logradouro ) VALUES 
(1111, 29584878, 52, 'Alameda 20', 'Alameda'),
(2222, 29182528, 2, 'Travessa II', 'Travessa'),
(3333, 29547698, 69, 'Travessa III', 'Travessa'),
(4444, 29114447, 1000, 'Av. Princesa', 'Avenida');

INSERT INTO pessoa(id_pessoa, id_telefone, id_endereco, nome_pessoa, cpf) VALUES 
(100, 1, 1111, 'Alfredo', 812546),
(200, 2, 2222, 'Thomas', 231375),
(300, 3, 3333, 'José', 312345),
(400, 4, 4444, 'Luciano', 432131);

ALTER TABLE contato ADD id_pessoa int;
ALTER TABLE agenda ADD CONSTRAINT id_exame  FOREIGN KEY (id_exame) REFERENCES exame(id_exame );

UPDATE contato SET id_pessoa = 100 WHERE id_telefone = 1;
UPDATE contato SET id_pessoa = 200 WHERE id_telefone = 2;
UPDATE contato SET id_pessoa = 300 WHERE id_telefone = 3;
UPDATE contato SET id_pessoa = 400 WHERE id_telefone = 4;

ALTER TABLE endereco ADD id_pessoa int;
ALTER TABLE endereco ADD CONSTRAINT id_pessoa FOREIGN KEY (id_pessoa ) REFERENCES pessoa(id_pessoa );

UPDATE endereco SET id_pessoa = 100 WHERE id_endereco = 1111;
UPDATE endereco SET id_pessoa = 200 WHERE id_endereco = 2222;
UPDATE endereco SET id_pessoa = 300 WHERE id_endereco = 3333;
UPDATE endereco SET id_pessoa = 400 WHERE id_endereco = 4444;


INSERT INTO paciente(id_paciente , id_pessoa) VALUES 
(11111, 100),
(22222, 200),
(33333, 300),
(44444, 400);

INSERT INTO funcionario(id_funcionario, id_pessoa, carga_horaria, tipo_funcionario) VALUES 
(1010, 100, 8, 'Médico'),
(2020, 200, 8, 'Enfermeiro');

INSERT INTO agenda(id_agendamento , id_paciente , data_exame) VALUES 
(1212, 33333, '2020-08-30'),
(2323, 44444, '2020-09-20');

INSERT INTO exame(id_exame , id_funcionario , id_agendamento, tipo_exame, status) VALUES 
(101010, 1010, 1212,'COVID', 'PROCESSO'),
(202020, 2020, 2323,'SANGUE', 'PROCESSO');

INSERT INTO resultado(id_resultado , id_exame) VALUES 
(134, 101010),
(156, 202020);

ALTER TABLE agenda ADD id_exame int;
ALTER TABLE agenda ADD CONSTRAINT id_exame FOREIGN KEY (id_exame) REFERENCES exame(id_exame);


UPDATE agenda SET id_exame = 101010 WHERE id_agenda  = 1212;
UPDATE agenda SET id_exame = 202020 WHERE id_agenda  = 2323;
```

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

1-) SELECT * FROM contato;
https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/select%20contato.png


># Marco de Entrega 01: Do item 1 até o item 9.1<br>

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    a) Criar minimo 3 de exclusão
    b) Criar minimo 3 de atualização

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    a) Criar minimo 2 envolvendo algum tipo de junção

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho

#### 9.10	SUBCONSULTAS (Mínimo 4)<br>
     a) Criar minimo 1 envolvendo GROUP BY
     b) Criar minimo 1 envolvendo algum tipo de junção

># Marco de Entrega 02: Do item 9.2 até o ítem 9.10<br>

### 10 RELATÓRIOS E GRÁFICOS

#### a) análises e resultados provenientes do banco de dados desenvolvido (usar modelo disponível)
#### b) link com exemplo de relatórios será disponiblizado pelo professor no AVA
#### OBS: Esta é uma atividade de grande relevância no contexto do trabalho. Mantenha o foco nos 5 principais relatórios/resultados visando obter o melhor resultado possível.

    

### 11	AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇAO FINAL <br>

#### a) Modelo (pecha kucha)<br>
#### b) Tempo de apresentação 6:40 

># Marco de Entrega 03: Itens 10 e 11<br>
<br>
<br>
<br> 



### 12 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
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
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://www.sis4.com/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


